# SocketSendWithReplacement(char *,unsigned __int64 *,sockaddr *)

- ea: `0x180015530`
- end: `0x180015836`
- name: `?SocketSendWithReplacement@@YAXPEADPEA_KPEAUsockaddr@@@Z`
- size: `774`
- prototype: `void __fastcall(char *, unsigned __int64 *, struct sockaddr *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800025f0`

## callees

- `0x18000ddb0`
- `0x180015530`
- `0x180015bd8`
- `0x180015ea8`
- `0x180015f20`
- `0x1800287d0`
- `0x18002911c`
- `0x18002fe28`
- `0x180031278`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180015693`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180015693`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800155f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800155f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800155ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800155ca`
- `WS2_32!__imp_getsockname` at `0x180015588`
- `WS2_32!__imp_getsockname` at `0x180015588`
- `WS2_32!__imp_WSAGetLastError` at `0x1800156c6`
- `WS2_32!__imp_WSAGetLastError` at `0x1800156fb`
- `WS2_32!__imp_WSAGetLastError` at `0x1800156c6`
- `WS2_32!__imp_WSAGetLastError` at `0x1800156fb`

## pseudocode

```c
void __fastcall SocketSendWithReplacement(char *a1, unsigned __int64 *a2, struct sockaddr *a3)
{
  SOCKET v6; // rcx
  struct _SSDPNetwork *SSDPNetwork; // rbx
  int v8; // edi
  void *v9; // rbx
  SOCKET v10; // rdx
  int Error; // eax
  bool v12; // zf
  int v13; // eax
  int i; // r10d
  int v15; // r10d
  int namelen; // [rsp+40h] [rbp-C8h] BYREF
  void *Block; // [rsp+48h] [rbp-C0h] BYREF
  struct sockaddr name; // [rsp+50h] [rbp-B8h] BYREF

  Block = 0;
  memset_0(&name, 0, 0x80u);
  v6 = *a2;
  namelen = 128;
  if ( getsockname(v6, &name, &namelen) == -1 )
  {
    Error = WSAGetLastError();
    v12 = Error == 0;
    if ( Error > 0 )
      v12 = 0;
    if ( !v12 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      v13 = WSAGetLastError();
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids, a2, v13);
    }
  }
  else
  {
    SSDPNetwork = FindSSDPNetwork(&name);
    if ( SSDPNetwork )
    {
      EnterCriticalSection(&CUPnPInterfaceList::s_instance);
      if ( HIDWORD(xmmword_180044C10) )
      {
        v8 = 0;
        for ( i = 0; i < (int)qword_180044BD0; i = v15 + 1 )
        {
          if ( (unsigned int)IPAddressIsEqual((const struct sockaddr *)(qword_180044BC8 + ((__int64)i << 7)), &name) )
          {
            v8 = 1;
            break;
          }
        }
      }
      else
      {
        v8 = DWORD2(xmmword_180044C10);
      }
      LeaveCriticalSection(&CUPnPInterfaceList::s_instance);
      if ( v8
        && (unsigned int)FReplaceTokenInLocation(
                           a1,
                           *((char **)SSDPNetwork + 28),
                           *((_DWORD *)SSDPNetwork + 58),
                           (char *)SSDPNetwork + 184,
                           *((_DWORD *)SSDPNetwork + 55),
                           0,
                           *((_DWORD *)SSDPNetwork + 59),
                           (char **)&Block) )
      {
        v9 = Block;
        v10 = *a2;
        if ( Block )
        {
          if ( (unsigned int)SocketSend((const char *)Block, v10, a3)
            && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          {
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids, v9);
          }
          free(v9);
        }
        else if ( (unsigned int)SocketSend(a1, v10, a3)
               && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids, a1);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids,
        a2,
        -2147023728);
    }
  }
}

```

## disassembly

```asm
0x180015530  push    rbp
0x180015532  push    rsi
0x180015533  push    r14
0x180015535  push    r15
0x180015537  sub     rsp, 0E8h
0x18001553e  mov     rax, cs:__security_cookie
0x180015545  xor     rax, rsp
0x180015548  mov     [rsp+108h+var_38], rax
0x180015550  mov     rbp, r8
0x180015553  mov     rsi, rdx
0x180015556  mov     r14, rcx
0x180015559  xor     r15d, r15d
0x18001555c  xor     edx, edx; Val
0x18001555e  mov     [rsp+108h+Block], r15
0x180015563  mov     r8d, 80h; Size
0x180015569  lea     rcx, [rsp+108h+name]; void *
0x18001556e  call    memset_0
0x180015573  mov     rcx, [rsi]; s
0x180015576  lea     r8, [rsp+108h+namelen]; namelen
0x18001557b  lea     rdx, [rsp+108h+name]; name
0x180015580  mov     [rsp+108h+namelen], 80h
0x180015588  call    cs:__imp_getsockname
0x18001558f  nop     dword ptr [rax+rax+00h]
0x180015594  cmp     eax, 0FFFFFFFFh
0x180015597  jz      loc_1800156C6
0x18001559d  lea     rcx, [rsp+108h+name]; struct sockaddr *
0x1800155a2  mov     [rsp+108h+arg_18], rbx
0x1800155aa  call    ?FindSSDPNetwork@@YAPEAU_SSDPNetwork@@PEAUsockaddr@@@Z; FindSSDPNetwork(sockaddr *)
0x1800155af  mov     rbx, rax
0x1800155b2  test    rax, rax
0x1800155b5  jz      loc_1800157E3
0x1800155bb  lea     rcx, ?s_instance@CUPnPInterfaceList@@0V1@A; lpCriticalSection
0x1800155c2  mov     [rsp+108h+var_28], rdi
0x1800155ca  call    cs:__imp_EnterCriticalSection
0x1800155d1  nop     dword ptr [rax+rax+00h]
0x1800155d6  cmp     dword ptr cs:xmmword_180044C10+0Ch, r15d
0x1800155dd  jnz     loc_180015737
0x1800155e3  mov     edi, dword ptr cs:xmmword_180044C10+8
0x1800155e9  lea     rcx, ?s_instance@CUPnPInterfaceList@@0V1@A; lpCriticalSection
0x1800155f0  call    cs:__imp_LeaveCriticalSection
0x1800155f7  nop     dword ptr [rax+rax+00h]
0x1800155fc  test    edi, edi
0x1800155fe  mov     rdi, [rsp+108h+var_28]
0x180015606  jz      loc_18001569F
0x18001560c  mov     r8d, [rbx+0E8h]; int
0x180015613  lea     rax, [rsp+108h+Block]
0x180015618  mov     rdx, [rbx+0E0h]; char *
0x18001561f  lea     r9, [rbx+0B8h]; char *
0x180015626  mov     [rsp+108h+var_D0], rax; char **
0x18001562b  mov     rcx, r14; char *
0x18001562e  mov     eax, [rbx+0ECh]
0x180015634  mov     [rsp+108h+var_D8], eax; unsigned int
0x180015638  mov     eax, [rbx+0DCh]
0x18001563e  mov     [rsp+108h+var_E0], r15d; int
0x180015643  mov     [rsp+108h+var_E8], eax; int
0x180015647  call    ?FReplaceTokenInLocation@@YAHPEBDPEADH1HHKPEAPEAD@Z; FReplaceTokenInLocation(char const *,char *,int,char *,int,int,ulong,char * *)
0x18001564c  test    eax, eax
0x18001564e  jz      short loc_18001569F
0x180015650  mov     rbx, [rsp+108h+Block]
0x180015655  mov     r8, rbp; lpsaAddress
0x180015658  mov     rdx, [rsi]; s
0x18001565b  test    rbx, rbx
0x18001565e  jz      loc_180015792
0x180015664  mov     rcx, rbx; buf
0x180015667  call    ?SocketSend@@YAHPEBD_KPEAUsockaddr@@@Z; SocketSend(char const *,unsigned __int64,sockaddr *)
0x18001566c  test    eax, eax
0x18001566e  jz      short loc_180015690
0x180015670  mov     rcx, cs:WPP_GLOBAL_Control
0x180015677  lea     rax, WPP_GLOBAL_Control
0x18001567e  cmp     rcx, rax
0x180015681  jz      short loc_180015690
0x180015683  test    dword ptr [rcx+1Ch], 200h
0x18001568a  jnz     loc_180015775
0x180015690  mov     rcx, rbx; Block
0x180015693  call    cs:__imp_free
0x18001569a  nop     dword ptr [rax+rax+00h]
0x18001569f  mov     rbx, [rsp+108h+arg_18]
0x1800156a7  mov     rcx, [rsp+108h+var_38]
0x1800156af  xor     rcx, rsp; StackCookie
0x1800156b2  call    __security_check_cookie
0x1800156b7  add     rsp, 0E8h
0x1800156be  pop     r15
0x1800156c0  pop     r14
0x1800156c2  pop     rsi
0x1800156c3  pop     rbp
0x1800156c4  retn
0x1800156c6  call    cs:__imp_WSAGetLastError
0x1800156cd  nop     dword ptr [rax+rax+00h]
0x1800156d2  test    eax, eax
0x1800156d4  jle     short loc_1800156E0
0x1800156d6  movzx   eax, ax
0x1800156d9  or      eax, 80070000h
0x1800156de  test    eax, eax
0x1800156e0  jz      short loc_1800156A7
0x1800156e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800156e9  lea     rax, WPP_GLOBAL_Control
0x1800156f0  cmp     rcx, rax
0x1800156f3  jz      short loc_1800156A7
0x1800156f5  test    byte ptr [rcx+1Ch], 1
0x1800156f9  jz      short loc_1800156A7
0x1800156fb  call    cs:__imp_WSAGetLastError
0x180015702  nop     dword ptr [rax+rax+00h]
0x180015707  test    eax, eax
0x180015709  jg      loc_180015829
0x18001570f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015716  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x18001571d  mov     edx, 2Ch ; ','
0x180015722  mov     [rsp+108h+var_E8], eax
0x180015726  mov     r9, rsi
0x180015729  mov     rcx, [rcx+10h]
0x18001572d  call    WPP_SF_qd
0x180015732  jmp     loc_1800156A7
0x180015737  mov     edi, r15d
0x18001573a  mov     r10d, r15d
0x18001573d  cmp     r10d, dword ptr cs:qword_180044BD0
0x180015744  jge     loc_1800155E9
0x18001574a  movsxd  rcx, r10d
0x18001574d  lea     rdx, [rsp+108h+name]; struct sockaddr *
0x180015752  shl     rcx, 7
0x180015756  add     rcx, cs:qword_180044BC8; struct sockaddr *
0x18001575d  call    ?IPAddressIsEqual@@YAHPEBUsockaddr@@0@Z; IPAddressIsEqual(sockaddr const *,sockaddr const *)
0x180015762  test    eax, eax
0x180015764  jnz     short loc_18001576B
0x180015766  inc     r10d
0x180015769  jmp     short loc_18001573D
0x18001576b  mov     edi, 1
0x180015770  jmp     loc_1800155E9
0x180015775  mov     rcx, [rcx+10h]
0x180015779  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x180015780  mov     edx, 29h ; ')'
0x180015785  mov     r9, rbx
0x180015788  call    WPP_SF_s
0x18001578d  jmp     loc_180015690
0x180015792  mov     rcx, r14; buf
0x180015795  call    ?SocketSend@@YAHPEBD_KPEAUsockaddr@@@Z; SocketSend(char const *,unsigned __int64,sockaddr *)
0x18001579a  test    eax, eax
0x18001579c  jz      loc_18001569F
0x1800157a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800157a9  lea     rax, WPP_GLOBAL_Control
0x1800157b0  cmp     rcx, rax
0x1800157b3  jz      loc_18001569F
0x1800157b9  test    dword ptr [rcx+1Ch], 200h
0x1800157c0  jz      loc_18001569F
0x1800157c6  mov     rcx, [rcx+10h]
0x1800157ca  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x1800157d1  mov     edx, 2Ah ; '*'
0x1800157d6  mov     r9, r14
0x1800157d9  call    WPP_SF_s
0x1800157de  jmp     loc_18001569F
0x1800157e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800157ea  lea     rax, WPP_GLOBAL_Control
0x1800157f1  cmp     rcx, rax
0x1800157f4  jz      loc_18001569F
0x1800157fa  test    byte ptr [rcx+1Ch], 1
0x1800157fe  jz      loc_18001569F
0x180015804  mov     rcx, [rcx+10h]
0x180015808  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x18001580f  mov     edx, 2Bh ; '+'
0x180015814  mov     [rsp+108h+var_E8], 80070490h
0x18001581c  mov     r9, rsi
0x18001581f  call    WPP_SF_qd
0x180015824  jmp     loc_18001569F
0x180015829  movzx   eax, ax
0x18001582c  or      eax, 80070000h
0x180015831  jmp     loc_18001570F
```
