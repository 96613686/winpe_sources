# WdipUnloadDM

- ea: `0x1800068f0`
- end: `0x180006a82`
- name: `WdipUnloadDM`
- size: `402`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180002e70`
- `0x180006a90`

## callees

- `0x180001080`
- `0x1800011d0`
- `0x180002ba0`
- `0x1800068f0`
- `0x18000f1c2`
- `0x18000f1f0`
- `0x180010010`

## import_xrefs

- `ntdll!NtAlpcDisconnectPort` at `0x1800069fc`
- `ntdll!NtAlpcDisconnectPort` at `0x1800069fc`
- `ntdll!NtAlpcQueryInformation` at `0x180006a18`
- `ntdll!NtAlpcQueryInformation` at `0x180006a18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800069ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800069ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006a36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006a36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a51`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800069cd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800069cd`

## pseudocode

```c
__int64 __fastcall WdipUnloadDM(__int64 a1)
{
  unsigned int v2; // edi
  bool v4; // zf
  HMODULE v5; // rcx
  __int64 v6; // rcx
  char *v7; // rdi
  int v8; // [rsp+30h] [rbp-F8h] BYREF
  __int128 v9; // [rsp+38h] [rbp-F0h] BYREF
  _BYTE v10[16]; // [rsp+50h] [rbp-D8h] BYREF
  int v11; // [rsp+60h] [rbp-C8h]
  __int64 v12; // [rsp+80h] [rbp-A8h]

  v2 = 255;
  v8 = 255;
  v9 = 0;
  memset_0(v10, 0, 0xB8u);
  if ( a1 )
  {
    v4 = (*(_BYTE *)(a1 + 80) & 0x10) == 0;
    v12 = a1;
    v11 = 2;
    if ( v4 )
    {
      WdipLowerPagePriorityThread(&v8);
      v2 = v8;
    }
    (*(void (__fastcall **)(_BYTE *, __int64))(a1 + 32))(v10, 1);
    if ( (*(_BYTE *)(a1 + 80) & 0x10) == 0 )
      WdipRevertPagePriorityThread(v2);
    v5 = *(HMODULE *)(a1 + 48);
    if ( v5 )
    {
      FreeLibrary(v5);
      *(_QWORD *)(a1 + 48) = 0;
    }
    *(_QWORD *)(a1 + 40) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_QWORD *)(a1 + 32) = 0;
    *(_DWORD *)(a1 + 96) = 0;
    EnterCriticalSection(&g_csWDI);
    v6 = *(_QWORD *)(a1 + 56);
    *(_DWORD *)(a1 + 16) = 0;
    NtAlpcDisconnectPort(v6, 0);
    NtAlpcQueryInformation(*(_QWORD *)(a1 + 56), 0, &v9, 16, 0);
    v7 = *(char **)(a1 + 56);
    *(_DWORD *)(a1 + 84) += DWORD1(v9) - 1;
    *(_QWORD *)(a1 + 56) = 0;
    LeaveCriticalSection(&g_csWDI);
    if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v7);
    return 0;
  }
  else
  {
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\sessions.cpp",
      (__int64)L"WdipUnloadDM",
      411,
      (const wchar_t *)L"Error = %d",
      87);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800068f0  mov     [rsp+arg_18], rbx
0x1800068f5  push    rdi
0x1800068f6  sub     rsp, 120h
0x1800068fd  mov     rax, cs:__security_cookie
0x180006904  xor     rax, rsp
0x180006907  mov     [rsp+128h+var_18], rax
0x18000690f  mov     rbx, rcx
0x180006912  xorps   xmm0, xmm0
0x180006915  mov     edi, 0FFh
0x18000691a  lea     rcx, [rsp+128h+var_D8]; void *
0x18000691f  xor     edx, edx; Val
0x180006921  mov     [rsp+128h+var_F8], edi
0x180006925  mov     r8d, 0B8h; Size
0x18000692b  movups  [rsp+128h+var_F0], xmm0
0x180006930  call    memset_0
0x180006935  test    rbx, rbx
0x180006938  jnz     short loc_18000696C
0x18000693a  lea     r9, aErrorD_0; "Error = %d"
0x180006941  mov     dword ptr [rsp+128h+Args], 57h ; 'W'; Args
0x180006949  mov     r8d, 19Bh; int
0x18000694f  lea     rdx, aWdipunloaddm; "WdipUnloadDM"
0x180006956  lea     rcx, aClientcoreBase_3; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000695d  call    WdipTraceError
0x180006962  mov     eax, 80070057h
0x180006967  jmp     loc_180006A61
0x18000696c  mov     [rsp+128h+arg_8], rbp
0x180006974  xor     ebp, ebp
0x180006976  test    byte ptr [rbx+50h], 10h
0x18000697a  mov     [rsp+128h+arg_10], rsi
0x180006982  mov     esi, ebp
0x180006984  mov     [rsp+128h+var_A8], rbx
0x18000698c  mov     [rsp+128h+var_C8], 2
0x180006994  jnz     short loc_1800069A4
0x180006996  lea     rcx, [rsp+128h+var_F8]
0x18000699b  call    WdipLowerPagePriorityThread
0x1800069a0  mov     edi, [rsp+128h+var_F8]
0x1800069a4  mov     rax, [rbx+20h]
0x1800069a8  lea     rcx, [rsp+128h+var_D8]
0x1800069ad  mov     edx, 1
0x1800069b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069b7  test    byte ptr [rbx+50h], 10h
0x1800069bb  jnz     short loc_1800069C4
0x1800069bd  mov     ecx, edi
0x1800069bf  call    WdipRevertPagePriorityThread
0x1800069c4  mov     rcx, [rbx+30h]; hLibModule
0x1800069c8  test    rcx, rcx
0x1800069cb  jz      short loc_1800069D7
0x1800069cd  call    cs:__imp_FreeLibrary
0x1800069d3  mov     [rbx+30h], rbp
0x1800069d7  mov     [rbx+28h], rbp
0x1800069db  lea     rcx, g_csWDI; lpCriticalSection
0x1800069e2  mov     [rbx+18h], rbp
0x1800069e6  mov     [rbx+20h], rbp
0x1800069ea  mov     [rbx+60h], ebp
0x1800069ed  call    cs:__imp_EnterCriticalSection
0x1800069f3  mov     rcx, [rbx+38h]
0x1800069f7  xor     edx, edx
0x1800069f9  mov     [rbx+10h], ebp
0x1800069fc  call    cs:__imp_NtAlpcDisconnectPort
0x180006a02  mov     rcx, [rbx+38h]
0x180006a06  lea     r8, [rsp+128h+var_F0]
0x180006a0b  mov     r9d, 10h
0x180006a11  mov     qword ptr [rsp+128h+Args], rbp
0x180006a16  xor     edx, edx
0x180006a18  call    cs:__imp_NtAlpcQueryInformation
0x180006a1e  mov     edx, dword ptr [rsp+128h+var_F0+4]
0x180006a22  lea     rcx, g_csWDI; lpCriticalSection
0x180006a29  mov     rdi, [rbx+38h]
0x180006a2d  dec     edx
0x180006a2f  add     [rbx+54h], edx
0x180006a32  mov     [rbx+38h], rbp
0x180006a36  call    cs:__imp_LeaveCriticalSection
0x180006a3c  mov     rbp, [rsp+128h+arg_8]
0x180006a44  lea     rdx, [rdi-1]
0x180006a48  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180006a4c  ja      short loc_180006A57
0x180006a4e  mov     rcx, rdi; hObject
0x180006a51  call    cs:__imp_CloseHandle
0x180006a57  mov     eax, esi
0x180006a59  mov     rsi, [rsp+128h+arg_10]
0x180006a61  mov     rcx, [rsp+128h+var_18]
0x180006a69  xor     rcx, rsp; StackCookie
0x180006a6c  call    __security_check_cookie
0x180006a71  mov     rbx, [rsp+128h+arg_18]
0x180006a79  add     rsp, 120h
0x180006a80  pop     rdi
0x180006a81  retn
```
