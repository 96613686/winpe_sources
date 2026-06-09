# TcpRIO::LoadRIOFunctionTable(_RIO_EXTENSION_FUNCTION_TABLE * *)

- ea: `0x1004576f0`
- end: `0x100457956`
- name: `?LoadRIOFunctionTable@TcpRIO@@IEAAKPEAPEAU_RIO_EXTENSION_FUNCTION_TABLE@@@Z`
- size: `614`
- prototype: `unsigned int __fastcall(TcpRIO *__hidden this, struct _RIO_EXTENSION_FUNCTION_TABLE **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x100459830`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x1004576f0`
- `0x100486af0`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004577e4`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004577e4`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1004578e2`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1004578e2`
- `sqldk!SystemThread_TlsIndex` at `0x10045778a`
- `sqldk!SystemThread_TlsOffset` at `0x100457793`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004577ae`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004577ae`
- `WS2_32!WSAIoctl` at `0x100457878`
- `WS2_32!WSAIoctl` at `0x100457878`
- `WS2_32!__imp_WSAGetLastError` at `0x100457883`
- `WS2_32!__imp_WSAGetLastError` at `0x100457883`

## string_xrefs

- `0x10045772a`: `sql\common\dk\sni\src\sni_tcprioprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TcpRIO::LoadRIOFunctionTable(
        TcpRIO *this,
        struct _RIO_EXTENSION_FUNCTION_TABLE **a2,
        __int64 a3,
        const wchar_t *a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 v8; // rax
  _OWORD *v9; // rax
  void *v10; // rdi
  int Error; // eax
  LPVOID lpvOutBuffer; // [rsp+20h] [rbp-98h]
  __int64 cbOutBuffer; // [rsp+28h] [rbp-90h]
  LPDWORD lpcbBytesReturned; // [rsp+30h] [rbp-88h]
  DWORD cbBytesReturned; // [rsp+50h] [rbp-68h] BYREF
  __int64 v17; // [rsp+58h] [rbp-60h]
  const char *v18; // [rsp+60h] [rbp-58h]
  const char *v19; // [rsp+68h] [rbp-50h]
  int v20; // [rsp+70h] [rbp-48h]
  _DWORD vInBuffer[4]; // [rsp+78h] [rbp-40h] BYREF

  v17 = -2;
  v18 = "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp";
  v19 = "TcpRIO::LoadRIOFunctionTable";
  v20 = 861;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
      "TcpRIO::LoadRIOFunctionTable",
      861,
      L"API|SNIpConn: %p{SNI_Conn*}",
      *((_QWORD *)this + 4));
  v6 = 0;
  if ( !*a2 )
  {
    v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v8 = *(_QWORD *)(v7 + 256);
    if ( !v8 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v8 = *(_QWORD *)(v7 + 256);
    }
    v9 = operator new(
           0x70u,
           *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v8 + 992) + 56LL) + 8LL),
           1,
           "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
           868,
           6u);
    v10 = v9;
    if ( v9 )
    {
      *v9 = 0;
      v9[1] = 0;
      v9[2] = 0;
      v9[3] = 0;
      v9[4] = 0;
      v9[5] = 0;
      v9[6] = 0;
      vInBuffer[0] = -2062950271;
      vInBuffer[1] = 1074108125;
      vInBuffer[2] = 782132657;
      vInBuffer[3] = 1067370472;
      cbBytesReturned = 0;
      if ( WSAIoctl(*((_QWORD *)this + 8), 0xC8000024, vInBuffer, 0x10u, v9, 0x70u, &cbBytesReturned, 0, 0) == -1 )
      {
        Error = WSAGetLastError();
        v6 = Error;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(lpcbBytesReturned) = Error;
          LODWORD(cbOutBuffer) = 0;
          LODWORD(lpvOutBuffer) = 7;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
            "TcpRIO::LoadRIOFunctionTable",
            892,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            lpvOutBuffer,
            cbOutBuffer,
            lpcbBytesReturned);
        }
        SNISetLastError(7u, v6, 0xC3B4u);
      }
      else if ( _InterlockedCompareExchange64((volatile signed __int64 *)a2, (signed __int64)v10, 0) )
      {
        operator delete(v10, 0x70u);
      }
    }
    else
    {
      v6 = 14;
    }
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(lpvOutBuffer) = v6;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
      "TcpRIO::LoadRIOFunctionTable",
      907,
      L"RET|SNI%d{WINERR}\n",
      lpvOutBuffer);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp", "TcpRIO::LoadRIOFunctionTable", 861, a4);
  return v6;
}

```

## disassembly

```asm
0x1004576f0  mov     r11, rsp
0x1004576f3  push    rsi
0x1004576f4  push    rdi
0x1004576f5  push    r12
0x1004576f7  push    r14
0x1004576f9  push    r15
0x1004576fb  sub     rsp, 90h
0x100457702  mov     qword ptr [r11-60h], 0FFFFFFFFFFFFFFFEh
0x10045770a  mov     [r11+18h], rbx
0x10045770e  mov     [r11+20h], rbp
0x100457712  mov     rax, cs:__security_cookie
0x100457719  xor     rax, rsp
0x10045771c  mov     [rsp+0B8h+var_30], rax
0x100457724  mov     rsi, rdx
0x100457727  mov     rbp, rcx
0x10045772a  lea     r14, aSqlCommonDkSni_21; "sql\\common\\dk\\sni\\src\\sni_tcpriopr"...
0x100457731  mov     [r11-58h], r14
0x100457735  lea     r15, aTcprioLoadriof; "TcpRIO::LoadRIOFunctionTable"
0x10045773c  mov     [r11-50h], r15
0x100457740  mov     [rsp+0B8h+var_48], 35Dh
0x100457748  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10045774f  jz      short loc_100457772
0x100457751  mov     rax, [rcx+20h]
0x100457755  mov     [rsp+0B8h+lpvOutBuffer], rax
0x10045775a  lea     r9, aApiSnipconnPSn_7; "API|SNIpConn: %p{SNI_Conn*}"
0x100457761  mov     r8d, 35Dh; int
0x100457767  mov     rdx, r15; char *
0x10045776a  mov     rcx, r14; char *
0x10045776d  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100457772  xor     r12d, r12d
0x100457775  mov     ebx, r12d
0x100457778  cmp     [rsi], rbx
0x10045777b  jnz     loc_1004578E8
0x100457781  mov     rdx, gs:58h
0x10045778a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100457791  mov     ecx, [rax]
0x100457793  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10045779a  mov     edi, [rax]
0x10045779c  add     rdi, [rdx+rcx*8]
0x1004577a0  mov     rax, [rdi+100h]
0x1004577a7  test    rax, rax
0x1004577aa  jnz     short loc_1004577BB
0x1004577ac  xor     ecx, ecx
0x1004577ae  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004577b4  mov     rax, [rdi+100h]
0x1004577bb  mov     rax, [rax+3E0h]
0x1004577c2  mov     rcx, [rax+38h]
0x1004577c6  mov     byte ptr [rsp+0B8h+cbOutBuffer], 6
0x1004577cb  mov     dword ptr [rsp+0B8h+lpvOutBuffer], 364h
0x1004577d3  mov     r9, r14
0x1004577d6  mov     r8d, 1
0x1004577dc  mov     rdx, [rcx+8]
0x1004577e0  lea     ecx, [r8+6Fh]
0x1004577e4  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x1004577ea  mov     rdi, rax
0x1004577ed  test    rax, rax
0x1004577f0  jnz     short loc_1004577FA
0x1004577f2  lea     ebx, [rax+0Eh]
0x1004577f5  jmp     loc_1004578E8
0x1004577fa  xorps   xmm0, xmm0
0x1004577fd  movups  xmmword ptr [rax], xmm0
0x100457800  movups  xmmword ptr [rax+10h], xmm0
0x100457804  movups  xmmword ptr [rax+20h], xmm0
0x100457808  movups  xmmword ptr [rax+30h], xmm0
0x10045780c  movups  xmmword ptr [rax+40h], xmm0
0x100457810  movups  xmmword ptr [rax+50h], xmm0
0x100457814  movups  xmmword ptr [rax+60h], xmm0
0x100457818  mov     [rsp+0B8h+vInBuffer], 8509E081h
0x100457820  mov     [rsp+0B8h+var_3C], 400596DDh
0x100457828  mov     [rsp+0B8h+var_38], 2E9E65B1h
0x100457833  mov     [rsp+0B8h+var_34], 3F9EC7E8h
0x10045783e  mov     [rsp+0B8h+cbBytesReturned], r12d
0x100457843  mov     [rsp+0B8h+lpCompletionRoutine], r12; lpCompletionRoutine
0x100457848  mov     [rsp+0B8h+lpOverlapped], r12; lpOverlapped
0x10045784d  lea     rax, [rsp+0B8h+cbBytesReturned]
0x100457852  mov     [rsp+0B8h+lpcbBytesReturned], rax; lpcbBytesReturned
0x100457857  mov     dword ptr [rsp+0B8h+cbOutBuffer], 70h ; 'p'; cbOutBuffer
0x10045785f  mov     [rsp+0B8h+lpvOutBuffer], rdi; lpvOutBuffer
0x100457864  mov     r9d, 10h; cbInBuffer
0x10045786a  lea     r8, [rsp+0B8h+vInBuffer]; lpvInBuffer
0x10045786f  mov     edx, 0C8000024h; dwIoControlCode
0x100457874  mov     rcx, [rbp+40h]; s
0x100457878  call    cs:__imp_WSAIoctl
0x10045787e  cmp     eax, 0FFFFFFFFh
0x100457881  jnz     short loc_1004578D1
0x100457883  call    cs:__imp_WSAGetLastError
0x100457889  mov     ebx, eax
0x10045788b  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100457892  jz      short loc_1004578BD
0x100457894  mov     dword ptr [rsp+0B8h+lpcbBytesReturned], eax
0x100457898  mov     dword ptr [rsp+0B8h+cbOutBuffer], r12d
0x10045789d  mov     dword ptr [rsp+0B8h+lpvOutBuffer], 7
0x1004578a5  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x1004578ac  mov     r8d, 37Ch; int
0x1004578b2  mov     rdx, r15; char *
0x1004578b5  mov     rcx, r14; char *
0x1004578b8  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004578bd  mov     r8d, 0C3B4h
0x1004578c3  mov     edx, ebx
0x1004578c5  mov     ecx, 7
0x1004578ca  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004578cf  jmp     short loc_1004578E8
0x1004578d1  xor     eax, eax
0x1004578d3  lock cmpxchg [rsi], rdi
0x1004578d8  jz      short loc_1004578E8
0x1004578da  mov     edx, 70h ; 'p'
0x1004578df  mov     rcx, rdi
0x1004578e2  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1004578e8  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004578ef  jz      short loc_10045790E
0x1004578f1  mov     dword ptr [rsp+0B8h+lpvOutBuffer], ebx
0x1004578f5  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004578fc  mov     r8d, 38Bh; int
0x100457902  mov     rdx, r15; char *
0x100457905  mov     rcx, r14; char *
0x100457908  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10045790d  nop
0x10045790e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100457915  jz      short loc_100457928
0x100457917  mov     r8d, 35Dh; int
0x10045791d  mov     rdx, r15; char *
0x100457920  mov     rcx, r14; char *
0x100457923  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100457928  mov     eax, ebx
0x10045792a  mov     rcx, [rsp+0B8h+var_30]
0x100457932  xor     rcx, rsp; StackCookie
0x100457935  call    __security_check_cookie
0x10045793a  lea     r11, [rsp+0B8h+var_28]
0x100457942  mov     rbx, [r11+40h]
0x100457946  mov     rbp, [r11+48h]
0x10045794a  mov     rsp, r11
0x10045794d  pop     r15
0x10045794f  pop     r14
0x100457951  pop     r12
0x100457953  pop     rdi
0x100457954  pop     rsi
0x100457955  retn
```
