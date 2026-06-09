# CDlpStateXml::~CDlpStateXml(void)

- ea: `0x1800459a0`
- end: `0x180045b18`
- name: `??1CDlpStateXml@@EEAA@XZ`
- size: `376`
- prototype: `void __fastcall(CDlpStateXml *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180046ac0`

## callees

- `0x18001fd60`
- `0x1800459a0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180045a15`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180045a24`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180045a15`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180045a24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045a63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045a90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045abd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045a63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045a90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045abd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045a72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045a9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045acc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045a72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045a9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045acc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045b00`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045b00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800459ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045a02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045a38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045a50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800459ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045a02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045a38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045a50`
- `UNATTEND!UnattendCtxCleanup` at `0x1800459c9`
- `UNATTEND!UnattendCtxCleanup` at `0x1800459c9`

## pseudocode

```c
void __fastcall CDlpStateXml::~CDlpStateXml(CDlpStateXml *this)
{
  char *v2; // rcx
  char *v3; // rcx
  const WCHAR *v4; // rcx
  const WCHAR *v5; // rcx
  char *v6; // rcx
  char *v7; // rcx
  __int64 v8; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v10; // rbx
  HANDLE v11; // rax
  __int64 v12; // rbx
  HANDLE v13; // rax

  *(_QWORD *)this = &CDlpStateXml::`vftable'{for `IUnknown'};
  *((_QWORD *)this + 1) = &CDlpStateXml::`vftable'{for `IDlpProperties'};
  UnattendCtxCleanup((char *)this + 136);
  if ( *((_DWORD *)this + 37) )
  {
    v2 = (char *)*((_QWORD *)this + 13);
    if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v2);
      *((_QWORD *)this + 13) = -1;
    }
    v3 = (char *)*((_QWORD *)this + 14);
    if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v3);
      *((_QWORD *)this + 14) = -1;
    }
    v4 = (const WCHAR *)*((_QWORD *)this + 10);
    if ( v4 )
      DeleteFileW(v4);
    v5 = (const WCHAR *)*((_QWORD *)this + 11);
    if ( v5 )
      DeleteFileW(v5);
  }
  v6 = (char *)*((_QWORD *)this + 14);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 14) = -1;
  }
  v7 = (char *)*((_QWORD *)this + 13);
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 13) = -1;
  }
  v8 = *((_QWORD *)this + 12);
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v8 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 12) = 0;
  }
  v10 = *((_QWORD *)this + 11);
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, (LPVOID)(v10 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 11) = 0;
  }
  v12 = *((_QWORD *)this + 10);
  if ( v12 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, (LPVOID)(v12 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 10) = 0;
  }
  *(_QWORD *)this = &CUnknownImpl<IDlpObjectData>::`vftable'{for `IUnknown'};
  *((_QWORD *)this + 1) = &CUnknownImpl<IDlpManagerInternal>::`vftable'{for `IDlpProperties'};
  if ( *((_DWORD *)this + 18) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *((_DWORD *)this + 18) = 0;
  }
}

```

## disassembly

```asm
0x1800459a0  mov     [rsp+arg_0], rbx
0x1800459a5  push    rdi
0x1800459a6  sub     rsp, 20h
0x1800459aa  lea     rax, ??_7CDlpStateXml@@6BIUnknown@@@; const CDlpStateXml::`vftable'{for `IUnknown'}
0x1800459b1  mov     rdi, rcx
0x1800459b4  mov     [rcx], rax
0x1800459b7  lea     rax, ??_7CDlpStateXml@@6BIDlpProperties@@@; const CDlpStateXml::`vftable'{for `IDlpProperties'}
0x1800459be  mov     [rcx+8], rax
0x1800459c2  add     rcx, 88h
0x1800459c9  call    cs:__imp_UnattendCtxCleanup
0x1800459cf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800459d3  cmp     dword ptr [rdi+94h], 0
0x1800459da  jz      short loc_180045A2A
0x1800459dc  mov     rcx, [rdi+68h]; hObject
0x1800459e0  lea     rax, [rcx-1]
0x1800459e4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800459e8  ja      short loc_1800459F4
0x1800459ea  call    cs:__imp_CloseHandle
0x1800459f0  mov     [rdi+68h], rbx
0x1800459f4  mov     rcx, [rdi+70h]; hObject
0x1800459f8  lea     rax, [rcx-1]
0x1800459fc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180045a00  ja      short loc_180045A0C
0x180045a02  call    cs:__imp_CloseHandle
0x180045a08  mov     [rdi+70h], rbx
0x180045a0c  mov     rcx, [rdi+50h]; lpFileName
0x180045a10  test    rcx, rcx
0x180045a13  jz      short loc_180045A1B
0x180045a15  call    cs:__imp_DeleteFileW
0x180045a1b  mov     rcx, [rdi+58h]; lpFileName
0x180045a1f  test    rcx, rcx
0x180045a22  jz      short loc_180045A2A
0x180045a24  call    cs:__imp_DeleteFileW
0x180045a2a  mov     rcx, [rdi+70h]; hObject
0x180045a2e  lea     rax, [rcx-1]
0x180045a32  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180045a36  ja      short loc_180045A42
0x180045a38  call    cs:__imp_CloseHandle
0x180045a3e  mov     [rdi+70h], rbx
0x180045a42  mov     rcx, [rdi+68h]; hObject
0x180045a46  lea     rax, [rcx-1]
0x180045a4a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180045a4e  ja      short loc_180045A5A
0x180045a50  call    cs:__imp_CloseHandle
0x180045a56  mov     [rdi+68h], rbx
0x180045a5a  mov     rbx, [rdi+60h]
0x180045a5e  test    rbx, rbx
0x180045a61  jz      short loc_180045A87
0x180045a63  call    cs:__imp_GetProcessHeap
0x180045a69  lea     r8, [rbx-4]; lpMem
0x180045a6d  xor     edx, edx; dwFlags
0x180045a6f  mov     rcx, rax; hHeap
0x180045a72  call    cs:__imp_HeapFree
0x180045a78  xor     ecx, ecx
0x180045a7a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180045a7f  mov     qword ptr [rdi+60h], 0
0x180045a87  mov     rbx, [rdi+58h]
0x180045a8b  test    rbx, rbx
0x180045a8e  jz      short loc_180045AB4
0x180045a90  call    cs:__imp_GetProcessHeap
0x180045a96  lea     r8, [rbx-4]; lpMem
0x180045a9a  xor     edx, edx; dwFlags
0x180045a9c  mov     rcx, rax; hHeap
0x180045a9f  call    cs:__imp_HeapFree
0x180045aa5  xor     ecx, ecx
0x180045aa7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180045aac  mov     qword ptr [rdi+58h], 0
0x180045ab4  mov     rbx, [rdi+50h]
0x180045ab8  test    rbx, rbx
0x180045abb  jz      short loc_180045AE1
0x180045abd  call    cs:__imp_GetProcessHeap
0x180045ac3  lea     r8, [rbx-4]; lpMem
0x180045ac7  xor     edx, edx; dwFlags
0x180045ac9  mov     rcx, rax; hHeap
0x180045acc  call    cs:__imp_HeapFree
0x180045ad2  xor     ecx, ecx
0x180045ad4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180045ad9  mov     qword ptr [rdi+50h], 0
0x180045ae1  lea     rax, ??_7?$CUnknownImpl@VIDlpObjectData@@@@6BIUnknown@@@; const CUnknownImpl<IDlpObjectData>::`vftable'{for `IUnknown'}
0x180045ae8  mov     [rdi], rax
0x180045aeb  lea     rax, ??_7?$CUnknownImpl@VIDlpManagerInternal@@@@6BIDlpProperties@@@; const CUnknownImpl<IDlpManagerInternal>::`vftable'{for `IDlpProperties'}
0x180045af2  mov     [rdi+8], rax
0x180045af6  cmp     dword ptr [rdi+48h], 0
0x180045afa  jz      short loc_180045B0D
0x180045afc  lea     rcx, [rdi+20h]; lpCriticalSection
0x180045b00  call    cs:__imp_DeleteCriticalSection
0x180045b06  mov     dword ptr [rdi+48h], 0
0x180045b0d  mov     rbx, [rsp+28h+arg_0]
0x180045b12  add     rsp, 20h
0x180045b16  pop     rdi
0x180045b17  retn
```
