# SocketSendWithReplacement(char *,unsigned __int64 *,sockaddr *)

- ea: `0x1800129b0`
- end: `0x180012cd7`
- name: `?SocketSendWithReplacement@@YAXPEADPEA_KPEAUsockaddr@@@Z`
- size: `807`
- prototype: `void __fastcall(char *, unsigned __int64 *, struct sockaddr *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180001530`

## callees

- `0x18000cab0`
- `0x1800129b0`
- `0x180013044`
- `0x1800132f8`
- `0x180026a30`
- `0x18002735c`
- `0x18002dcf4`
- `0x18002f028`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012b28`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012b28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012a4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012a8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012a4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012a8b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012a29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012a6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012a29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012a6b`
- `WS2_32!__imp_getsockname` at `0x180012a08`
- `WS2_32!__imp_getsockname` at `0x180012a08`
- `WS2_32!__imp_WSAGetLastError` at `0x180012b54`
- `WS2_32!__imp_WSAGetLastError` at `0x180012b83`
- `WS2_32!__imp_WSAGetLastError` at `0x180012b54`
- `WS2_32!__imp_WSAGetLastError` at `0x180012b83`

## pseudocode

```c
void __fastcall SocketSendWithReplacement(char *a1, unsigned __int64 *a2, struct sockaddr *a3)
{
  SOCKET v6; // rcx
  struct _SSDPNetwork **v7; // rbx
  struct _SSDPNetwork *v8; // r10
  struct _SSDPNetwork **v9; // r11
  int v10; // edi
  void *v11; // rbx
  SOCKET v12; // rdx
  int Error; // eax
  bool v14; // zf
  int v15; // eax
  struct _SSDPNetwork **v16; // r10
  int i; // r10d
  int v18; // r10d
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
    v14 = Error == 0;
    if ( Error > 0 )
      v14 = 0;
    if ( !v14 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      v15 = WSAGetLastError();
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids, a2, v15);
    }
  }
  else
  {
    v7 = 0;
    EnterCriticalSection(&stru_180042200);
    v8 = ::Block;
    v9 = &::Block;
    while ( v8 != (struct _SSDPNetwork *)v9 )
    {
      if ( (unsigned int)IPAddressIsEqual(&name, (const struct sockaddr *)((char *)v8 + 24)) )
      {
        v7 = v16;
        break;
      }
      v8 = *v16;
    }
    LeaveCriticalSection(&stru_180042200);
    if ( v7 )
    {
      EnterCriticalSection(&CUPnPInterfaceList::s_instance);
      if ( HIDWORD(xmmword_180041B10) )
      {
        v10 = 0;
        for ( i = 0; i < (int)qword_180041AD0; i = v18 + 1 )
        {
          if ( (unsigned int)IPAddressIsEqual((const struct sockaddr *)(qword_180041AC8 + ((__int64)i << 7)), &name) )
          {
            v10 = 1;
            break;
          }
        }
      }
      else
      {
        v10 = DWORD2(xmmword_180041B10);
      }
      LeaveCriticalSection(&CUPnPInterfaceList::s_instance);
      if ( v10
        && (unsigned int)FReplaceTokenInLocation(
                           a1,
                           (char *)v7[28],
                           *((_DWORD *)v7 + 58),
                           (char *)v7 + 184,
                           *((_DWORD *)v7 + 55),
                           0,
                           *((_DWORD *)v7 + 59),
                           (char **)&Block) )
      {
        v11 = Block;
        v12 = *a2;
        if ( Block )
        {
          if ( (unsigned int)SocketSend((const char *)Block, v12, a3)
            && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          {
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids, v11);
          }
          free(v11);
        }
        else if ( (unsigned int)SocketSend(a1, v12, a3)
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
0x1800129b0  push    rbp
0x1800129b2  push    rsi
0x1800129b3  push    r14
0x1800129b5  push    r15
0x1800129b7  sub     rsp, 0E8h
0x1800129be  mov     rax, cs:__security_cookie
0x1800129c5  xor     rax, rsp
0x1800129c8  mov     [rsp+108h+var_38], rax
0x1800129d0  mov     rbp, r8
0x1800129d3  mov     rsi, rdx
0x1800129d6  mov     r14, rcx
0x1800129d9  xor     r15d, r15d
0x1800129dc  xor     edx, edx; Val
0x1800129de  mov     [rsp+108h+Block], r15
0x1800129e3  mov     r8d, 80h; Size
0x1800129e9  lea     rcx, [rsp+108h+name]; void *
0x1800129ee  call    memset_0
0x1800129f3  mov     rcx, [rsi]; s
0x1800129f6  lea     r8, [rsp+108h+namelen]; namelen
0x1800129fb  lea     rdx, [rsp+108h+name]; name
0x180012a00  mov     [rsp+108h+namelen], 80h
0x180012a08  call    cs:__imp_getsockname
0x180012a0e  cmp     eax, 0FFFFFFFFh
0x180012a11  jz      loc_180012B54
0x180012a17  mov     [rsp+108h+arg_18], rbx
0x180012a1f  lea     rcx, stru_180042200; lpCriticalSection
0x180012a26  mov     ebx, r15d
0x180012a29  call    cs:__imp_EnterCriticalSection
0x180012a2f  mov     r10, cs:Block
0x180012a36  lea     r11, Block
0x180012a3d  cmp     r10, r11
0x180012a40  jnz     loc_180012BB6
0x180012a46  lea     rcx, stru_180042200; lpCriticalSection
0x180012a4d  call    cs:__imp_LeaveCriticalSection
0x180012a53  test    rbx, rbx
0x180012a56  jz      loc_180012C84
0x180012a5c  lea     rcx, ?s_instance@CUPnPInterfaceList@@0V1@A; lpCriticalSection
0x180012a63  mov     [rsp+108h+var_28], rdi
0x180012a6b  call    cs:__imp_EnterCriticalSection
0x180012a71  cmp     dword ptr cs:xmmword_180041B10+0Ch, r15d
0x180012a78  jnz     loc_180012BD8
0x180012a7e  mov     edi, dword ptr cs:xmmword_180041B10+8
0x180012a84  lea     rcx, ?s_instance@CUPnPInterfaceList@@0V1@A; lpCriticalSection
0x180012a8b  call    cs:__imp_LeaveCriticalSection
0x180012a91  test    edi, edi
0x180012a93  mov     rdi, [rsp+108h+var_28]
0x180012a9b  jz      loc_180012B2E
0x180012aa1  mov     r8d, [rbx+0E8h]; int
0x180012aa8  lea     rax, [rsp+108h+Block]
0x180012aad  mov     rdx, [rbx+0E0h]; char *
0x180012ab4  lea     r9, [rbx+0B8h]; char *
0x180012abb  mov     [rsp+108h+var_D0], rax; char **
0x180012ac0  mov     rcx, r14; char *
0x180012ac3  mov     eax, [rbx+0ECh]
0x180012ac9  mov     [rsp+108h+var_D8], eax; unsigned int
0x180012acd  mov     eax, [rbx+0DCh]
0x180012ad3  mov     [rsp+108h+var_E0], r15d; int
0x180012ad8  mov     [rsp+108h+var_E8], eax; int
0x180012adc  call    ?FReplaceTokenInLocation@@YAHPEBDPEADH1HHKPEAPEAD@Z; FReplaceTokenInLocation(char const *,char *,int,char *,int,int,ulong,char * *)
0x180012ae1  test    eax, eax
0x180012ae3  jz      short loc_180012B2E
0x180012ae5  mov     rbx, [rsp+108h+Block]
0x180012aea  mov     r8, rbp; lpsaAddress
0x180012aed  mov     rdx, [rsi]; s
0x180012af0  test    rbx, rbx
0x180012af3  jz      loc_180012C33
0x180012af9  mov     rcx, rbx; buf
0x180012afc  call    ?SocketSend@@YAHPEBD_KPEAUsockaddr@@@Z; SocketSend(char const *,unsigned __int64,sockaddr *)
0x180012b01  test    eax, eax
0x180012b03  jz      short loc_180012B25
0x180012b05  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b0c  lea     rax, WPP_GLOBAL_Control
0x180012b13  cmp     rcx, rax
0x180012b16  jz      short loc_180012B25
0x180012b18  test    dword ptr [rcx+1Ch], 200h
0x180012b1f  jnz     loc_180012C16
0x180012b25  mov     rcx, rbx; Block
0x180012b28  call    cs:__imp_free
0x180012b2e  mov     rbx, [rsp+108h+arg_18]
0x180012b36  mov     rcx, [rsp+108h+var_38]
0x180012b3e  xor     rcx, rsp; StackCookie
0x180012b41  call    __security_check_cookie
0x180012b46  add     rsp, 0E8h
0x180012b4d  pop     r15
0x180012b4f  pop     r14
0x180012b51  pop     rsi
0x180012b52  pop     rbp
0x180012b53  retn
0x180012b54  call    cs:__imp_WSAGetLastError
0x180012b5a  test    eax, eax
0x180012b5c  jle     short loc_180012B68
0x180012b5e  movzx   eax, ax
0x180012b61  or      eax, 80070000h
0x180012b66  test    eax, eax
0x180012b68  jz      short loc_180012B36
0x180012b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b71  lea     rax, WPP_GLOBAL_Control
0x180012b78  cmp     rcx, rax
0x180012b7b  jz      short loc_180012B36
0x180012b7d  test    byte ptr [rcx+1Ch], 1
0x180012b81  jz      short loc_180012B36
0x180012b83  call    cs:__imp_WSAGetLastError
0x180012b89  test    eax, eax
0x180012b8b  jg      loc_180012CCA
0x180012b91  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b98  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x180012b9f  mov     edx, 2Ch ; ','
0x180012ba4  mov     [rsp+108h+var_E8], eax
0x180012ba8  mov     r9, rsi
0x180012bab  mov     rcx, [rcx+10h]
0x180012baf  call    WPP_SF_qd
0x180012bb4  jmp     short loc_180012B36
0x180012bb6  lea     rdx, [r10+18h]; struct sockaddr *
0x180012bba  lea     rcx, [rsp+108h+name]; struct sockaddr *
0x180012bbf  call    ?IPAddressIsEqual@@YAHPEBUsockaddr@@0@Z; IPAddressIsEqual(sockaddr const *,sockaddr const *)
0x180012bc4  test    eax, eax
0x180012bc6  jnz     short loc_180012BD0
0x180012bc8  mov     r10, [r10]
0x180012bcb  jmp     loc_180012A3D
0x180012bd0  mov     rbx, r10
0x180012bd3  jmp     loc_180012A46
0x180012bd8  mov     edi, r15d
0x180012bdb  mov     r10d, r15d
0x180012bde  cmp     r10d, dword ptr cs:qword_180041AD0
0x180012be5  jge     loc_180012A84
0x180012beb  movsxd  rcx, r10d
0x180012bee  lea     rdx, [rsp+108h+name]; struct sockaddr *
0x180012bf3  shl     rcx, 7
0x180012bf7  add     rcx, cs:qword_180041AC8; struct sockaddr *
0x180012bfe  call    ?IPAddressIsEqual@@YAHPEBUsockaddr@@0@Z; IPAddressIsEqual(sockaddr const *,sockaddr const *)
0x180012c03  test    eax, eax
0x180012c05  jnz     short loc_180012C0C
0x180012c07  inc     r10d
0x180012c0a  jmp     short loc_180012BDE
0x180012c0c  mov     edi, 1
0x180012c11  jmp     loc_180012A84
0x180012c16  mov     rcx, [rcx+10h]
0x180012c1a  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x180012c21  mov     edx, 29h ; ')'
0x180012c26  mov     r9, rbx
0x180012c29  call    WPP_SF_s
0x180012c2e  jmp     loc_180012B25
0x180012c33  mov     rcx, r14; buf
0x180012c36  call    ?SocketSend@@YAHPEBD_KPEAUsockaddr@@@Z; SocketSend(char const *,unsigned __int64,sockaddr *)
0x180012c3b  test    eax, eax
0x180012c3d  jz      loc_180012B2E
0x180012c43  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c4a  lea     rax, WPP_GLOBAL_Control
0x180012c51  cmp     rcx, rax
0x180012c54  jz      loc_180012B2E
0x180012c5a  test    dword ptr [rcx+1Ch], 200h
0x180012c61  jz      loc_180012B2E
0x180012c67  mov     rcx, [rcx+10h]
0x180012c6b  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x180012c72  mov     edx, 2Ah ; '*'
0x180012c77  mov     r9, r14
0x180012c7a  call    WPP_SF_s
0x180012c7f  jmp     loc_180012B2E
0x180012c84  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c8b  lea     rax, WPP_GLOBAL_Control
0x180012c92  cmp     rcx, rax
0x180012c95  jz      loc_180012B2E
0x180012c9b  test    byte ptr [rcx+1Ch], 1
0x180012c9f  jz      loc_180012B2E
0x180012ca5  mov     rcx, [rcx+10h]
0x180012ca9  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x180012cb0  mov     edx, 2Bh ; '+'
0x180012cb5  mov     [rsp+108h+var_E8], 80070490h
0x180012cbd  mov     r9, rsi
0x180012cc0  call    WPP_SF_qd
0x180012cc5  jmp     loc_180012B2E
0x180012cca  movzx   eax, ax
0x180012ccd  or      eax, 80070000h
0x180012cd2  jmp     loc_180012B91
```
