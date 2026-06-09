# TcpConnection::LoadConnectEx(__CONNECTEXFUNC * *)

- ea: `0x1004359c0`
- end: `0x100435bda`
- name: `?LoadConnectEx@TcpConnection@@AEAAKPEAPEAU__CONNECTEXFUNC@@@Z`
- size: `538`
- prototype: `unsigned int __fastcall(TcpConnection *__hidden this, struct __CONNECTEXFUNC **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100435d20`

## callees

- `0x10042b7f0`
- `0x10042c270`
- `0x10042c430`
- `0x1004359c0`
- `0x100486af0`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100435ab5`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100435ab5`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100435b56`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100435b56`
- `sqldk!SystemThread_TlsIndex` at `0x100435a5b`
- `sqldk!SystemThread_TlsOffset` at `0x100435a64`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100435a7f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100435a7f`
- `WS2_32!WSAIoctl` at `0x100435b2f`
- `WS2_32!WSAIoctl` at `0x100435b2f`
- `WS2_32!__imp_WSAGetLastError` at `0x100435b3a`
- `WS2_32!__imp_WSAGetLastError` at `0x100435b3a`

## string_xrefs

- `0x1004359fa`: `sql\common\dk\sni\src\tcp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TcpConnection::LoadConnectEx(
        TcpConnection *this,
        struct __CONNECTEXFUNC **a2,
        __int64 a3,
        const wchar_t *a4)
{
  __int64 v6; // rbp
  unsigned int Error; // edi
  __int64 v8; // rsi
  __int64 v9; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rsi
  LPVOID lpvOutBuffer; // [rsp+20h] [rbp-98h]
  DWORD cbBytesReturned; // [rsp+50h] [rbp-68h] BYREF
  __int64 v15; // [rsp+58h] [rbp-60h]
  const char *v16; // [rsp+60h] [rbp-58h]
  const char *v17; // [rsp+68h] [rbp-50h]
  int v18; // [rsp+70h] [rbp-48h]
  _DWORD vInBuffer[4]; // [rsp+78h] [rbp-40h] BYREF

  v15 = -2;
  v16 = "sql\\common\\dk\\sni\\src\\tcp.cpp";
  v17 = "TcpConnection::LoadConnectEx";
  v18 = 3080;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\tcp.cpp",
      "TcpConnection::LoadConnectEx",
      3080,
      L"API|SNI%u#, ppfnCF: %p{CONNECTEXFUNC**}\n",
      *((_DWORD *)this + 11),
      a2);
  v6 = 0;
  Error = 0;
  if ( !*a2 )
  {
    v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v9 = *(_QWORD *)(v8 + 256);
    if ( !v9 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v9 = *(_QWORD *)(v8 + 256);
    }
    v10 = operator new(
            8u,
            *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v9 + 992) + 56LL) + 8LL),
            1,
            "sql\\common\\dk\\sni\\src\\tcp.cpp",
            3087,
            6u);
    v11 = v10;
    if ( v10 )
    {
      *v10 = 0;
      vInBuffer[0] = 631375801;
      vInBuffer[1] = 1180753395;
      vInBuffer[2] = -445191794;
      vInBuffer[3] = 1040610444;
      cbBytesReturned = 0;
      if ( WSAIoctl(*((_QWORD *)this + 3), 0xC8000006, vInBuffer, 0x10u, v10, 8u, &cbBytesReturned, 0, 0) == -1 )
      {
        Error = WSAGetLastError();
        *v11 = 0;
      }
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)a2, (signed __int64)v11, 0) )
        operator delete(v11, 8u);
    }
    else
    {
      Error = 14;
    }
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    if ( *a2 )
      v6 = *(_QWORD *)*a2;
    LODWORD(lpvOutBuffer) = Error;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\tcp.cpp",
      "TcpConnection::LoadConnectEx",
      3158,
      L"RET|SNI%d{WINERR}, ConnectExFn: %p{LPFN_CONNECTEX}\n",
      lpvOutBuffer,
      v6);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "TcpConnection::LoadConnectEx", 3080, a4);
  return Error;
}

```

## disassembly

```asm
0x1004359c0  mov     r11, rsp
0x1004359c3  push    rsi
0x1004359c4  push    rdi
0x1004359c5  push    r12
0x1004359c7  push    r14
0x1004359c9  push    r15
0x1004359cb  sub     rsp, 90h
0x1004359d2  mov     qword ptr [r11-60h], 0FFFFFFFFFFFFFFFEh
0x1004359da  mov     [r11+18h], rbx
0x1004359de  mov     [r11+20h], rbp
0x1004359e2  mov     rax, cs:__security_cookie
0x1004359e9  xor     rax, rsp
0x1004359ec  mov     [rsp+0B8h+var_30], rax
0x1004359f4  mov     rbx, rdx
0x1004359f7  mov     r14, rcx
0x1004359fa  lea     r15, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x100435a01  mov     [r11-58h], r15
0x100435a05  lea     r12, aTcpconnectionL; "TcpConnection::LoadConnectEx"
0x100435a0c  mov     [r11-50h], r12
0x100435a10  mov     [rsp+0B8h+var_48], 0C08h
0x100435a18  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100435a1f  jz      short loc_100435A45
0x100435a21  mov     qword ptr [rsp+0B8h+cbOutBuffer], rdx
0x100435a26  mov     eax, [rcx+2Ch]
0x100435a29  mov     dword ptr [rsp+0B8h+lpvOutBuffer], eax
0x100435a2d  lea     r9, aApiSniUPpfncfP; "API|SNI%u#, ppfnCF: %p{CONNECTEXFUNC**}"...
0x100435a34  mov     r8d, 0C08h; int
0x100435a3a  mov     rdx, r12; char *
0x100435a3d  mov     rcx, r15; char *
0x100435a40  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100435a45  xor     ebp, ebp
0x100435a47  mov     edi, ebp
0x100435a49  cmp     [rbx], rdi
0x100435a4c  jnz     loc_100435B5C
0x100435a52  mov     rdx, gs:58h
0x100435a5b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100435a62  mov     ecx, [rax]
0x100435a64  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100435a6b  mov     esi, [rax]
0x100435a6d  add     rsi, [rdx+rcx*8]
0x100435a71  mov     rax, [rsi+100h]
0x100435a78  test    rax, rax
0x100435a7b  jnz     short loc_100435A8C
0x100435a7d  xor     ecx, ecx
0x100435a7f  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100435a85  mov     rax, [rsi+100h]
0x100435a8c  mov     rax, [rax+3E0h]
0x100435a93  mov     rcx, [rax+38h]
0x100435a97  mov     byte ptr [rsp+0B8h+cbOutBuffer], 6
0x100435a9c  mov     dword ptr [rsp+0B8h+lpvOutBuffer], 0C0Fh
0x100435aa4  mov     r9, r15
0x100435aa7  mov     r8d, 1
0x100435aad  mov     rdx, [rcx+8]
0x100435ab1  lea     ecx, [r8+7]
0x100435ab5  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100435abb  mov     rsi, rax
0x100435abe  test    rax, rax
0x100435ac1  jnz     short loc_100435ACB
0x100435ac3  lea     edi, [rax+0Eh]
0x100435ac6  jmp     loc_100435B5C
0x100435acb  xor     eax, eax
0x100435acd  mov     [rsi], rax
0x100435ad0  mov     [rsp+0B8h+vInBuffer], 25A207B9h
0x100435ad8  mov     [rsp+0B8h+var_3C], 4660DDF3h
0x100435ae0  mov     [rsp+0B8h+var_38], 0E576E98Eh
0x100435aeb  mov     [rsp+0B8h+var_34], 3E06748Ch
0x100435af6  mov     [rsp+0B8h+cbBytesReturned], ebp
0x100435afa  mov     [rsp+0B8h+lpCompletionRoutine], rbp; lpCompletionRoutine
0x100435aff  mov     [rsp+0B8h+lpOverlapped], rbp; lpOverlapped
0x100435b04  lea     rax, [rsp+0B8h+cbBytesReturned]
0x100435b09  mov     [rsp+0B8h+lpcbBytesReturned], rax; lpcbBytesReturned
0x100435b0e  mov     [rsp+0B8h+cbOutBuffer], 8; cbOutBuffer
0x100435b16  mov     [rsp+0B8h+lpvOutBuffer], rsi; lpvOutBuffer
0x100435b1b  mov     r9d, 10h; cbInBuffer
0x100435b21  lea     r8, [rsp+0B8h+vInBuffer]; lpvInBuffer
0x100435b26  mov     edx, 0C8000006h; dwIoControlCode
0x100435b2b  mov     rcx, [r14+18h]; s
0x100435b2f  call    cs:__imp_WSAIoctl
0x100435b35  cmp     eax, 0FFFFFFFFh
0x100435b38  jnz     short loc_100435B45
0x100435b3a  call    cs:__imp_WSAGetLastError
0x100435b40  mov     edi, eax
0x100435b42  mov     [rsi], rbp
0x100435b45  xor     eax, eax
0x100435b47  lock cmpxchg [rbx], rsi
0x100435b4c  jz      short loc_100435B5C
0x100435b4e  mov     edx, 8
0x100435b53  mov     rcx, rsi
0x100435b56  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100435b5c  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100435b63  jz      short loc_100435B92
0x100435b65  mov     rax, [rbx]
0x100435b68  test    rax, rax
0x100435b6b  jz      short loc_100435B70
0x100435b6d  mov     rbp, [rax]
0x100435b70  mov     qword ptr [rsp+0B8h+cbOutBuffer], rbp
0x100435b75  mov     dword ptr [rsp+0B8h+lpvOutBuffer], edi
0x100435b79  lea     r9, aRetSniDWinerrC; "RET|SNI%d{WINERR}, ConnectExFn: %p{LPFN"...
0x100435b80  mov     r8d, 0C56h; int
0x100435b86  mov     rdx, r12; char *
0x100435b89  mov     rcx, r15; char *
0x100435b8c  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100435b91  nop
0x100435b92  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100435b99  jz      short loc_100435BAC
0x100435b9b  mov     r8d, 0C08h; int
0x100435ba1  mov     rdx, r12; char *
0x100435ba4  mov     rcx, r15; char *
0x100435ba7  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100435bac  mov     eax, edi
0x100435bae  mov     rcx, [rsp+0B8h+var_30]
0x100435bb6  xor     rcx, rsp; StackCookie
0x100435bb9  call    __security_check_cookie
0x100435bbe  lea     r11, [rsp+0B8h+var_28]
0x100435bc6  mov     rbx, [r11+40h]
0x100435bca  mov     rbp, [r11+48h]
0x100435bce  mov     rsp, r11
0x100435bd1  pop     r15
0x100435bd3  pop     r14
0x100435bd5  pop     r12
0x100435bd7  pop     rdi
0x100435bd8  pop     rsi
0x100435bd9  retn
```
