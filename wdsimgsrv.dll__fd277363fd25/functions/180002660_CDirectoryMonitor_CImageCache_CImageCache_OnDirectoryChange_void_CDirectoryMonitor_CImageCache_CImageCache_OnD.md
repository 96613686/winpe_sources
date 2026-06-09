# CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>::CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>(void)

- ea: `0x180002660`
- end: `0x1800026f1`
- name: `??0?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@QEAA@XZ`
- size: `145`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180007120`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000266d`
- `KERNEL32!InitializeCriticalSection` at `0x18000266d`
- `KERNEL32!GetSystemInfo` at `0x180002696`
- `KERNEL32!GetSystemInfo` at `0x180002696`

## pseudocode

```c
__int64 __fastcall CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>::CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>(
        __int64 a1)
{
  int v2; // eax
  __int64 result; // rax
  _SYSTEM_INFO SystemInfo; // [rsp+20h] [rbp-38h] BYREF

  InitializeCriticalSection((LPCRITICAL_SECTION)a1);
  *(_OWORD *)&SystemInfo.dwOemId = 0;
  *(_QWORD *)(a1 + 88) = 0;
  memset(&SystemInfo.lpMaximumApplicationAddress, 0, 32);
  GetSystemInfo(&SystemInfo);
  v2 = 1;
  if ( SystemInfo.dwNumberOfProcessors > 1 )
    v2 = 4;
  *(_DWORD *)(a1 + 96) = v2;
  result = a1;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_DWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 72) = -1;
  *(_DWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_DWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  return result;
}

```

## disassembly

```asm
0x180002660  mov     [rsp+arg_0], rbx
0x180002665  push    rdi
0x180002666  sub     rsp, 50h
0x18000266a  mov     rbx, rcx
0x18000266d  call    cs:__imp_InitializeCriticalSection
0x180002674  nop     dword ptr [rax+rax+00h]
0x180002679  xorps   xmm0, xmm0
0x18000267c  lea     rcx, [rsp+58h+SystemInfo]; lpSystemInfo
0x180002681  xor     edi, edi
0x180002683  movups  xmmword ptr [rsp+58h+SystemInfo], xmm0
0x180002688  mov     [rbx+58h], rdi
0x18000268c  movups  xmmword ptr [rsp+58h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180002691  movups  xmmword ptr [rsp+58h+SystemInfo.dwNumberOfProcessors], xmm0
0x180002696  call    cs:__imp_GetSystemInfo
0x18000269d  nop     dword ptr [rax+rax+00h]
0x1800026a2  lea     eax, [rdi+1]
0x1800026a5  cmp     [rsp+58h+SystemInfo.dwNumberOfProcessors], eax
0x1800026a9  lea     ecx, [rdi+4]
0x1800026ac  cmova   eax, ecx
0x1800026af  mov     [rbx+60h], eax
0x1800026b2  mov     rax, rbx
0x1800026b5  mov     [rbx+68h], rdi
0x1800026b9  mov     [rbx+70h], rdi
0x1800026bd  mov     [rbx+78h], rdi
0x1800026c1  mov     [rbx+88h], rdi
0x1800026c8  mov     [rbx+80h], edi
0x1800026ce  or      qword ptr [rbx+48h], 0FFFFFFFFFFFFFFFFh
0x1800026d3  mov     [rbx+28h], edi
0x1800026d6  mov     [rbx+30h], rdi
0x1800026da  mov     [rbx+38h], rdi
0x1800026de  mov     [rbx+40h], edi
0x1800026e1  mov     [rbx+50h], rdi
0x1800026e5  mov     rbx, [rsp+58h+arg_0]
0x1800026ea  add     rsp, 50h
0x1800026ee  pop     rdi
0x1800026ef  retn
```
