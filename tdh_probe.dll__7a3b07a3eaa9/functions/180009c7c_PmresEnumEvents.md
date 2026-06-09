# PmresEnumEvents

- ea: `0x180009c7c`
- end: `0x180009fe9`
- name: `PmresEnumEvents`
- size: `877`
- prototype: `__int64 __fastcall(int, __int64, const void *, PublisherManifestResource *, _OWORD *, char, unsigned int *, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180008970`

## callees

- `0x180009c7c`
- `0x180009ff0`
- `0x18000b508`
- `0x18000ba44`
- `0x18000bca4`
- `0x18000d560`
- `0x180012f34`
- `0x180020968`
- `0x180020974`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009eb3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009eb3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ea4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ea4`

## pseudocode

```c
__int64 __fastcall PmresEnumEvents(
        int a1,
        __int64 a2,
        const void *a3,
        PublisherManifestResource *a4,
        _OWORD *a5,
        char a6,
        unsigned int *a7,
        _QWORD *a8,
        unsigned int *a9)
{
  unsigned __int64 v9; // rdi
  unsigned int v10; // r12d
  __int64 v11; // rax
  struct EventResource *v12; // rsi
  int v13; // r15d
  unsigned int v14; // eax
  __int64 v15; // rbx
  __int64 v16; // rax
  unsigned __int64 v17; // kr10_8
  bool v18; // cf
  unsigned __int64 v19; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rdi
  unsigned int EventResource; // eax
  unsigned int TraceEventInfoManifest; // edi
  unsigned __int64 v27; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int64 v29; // rcx
  _QWORD *v30; // rsi
  unsigned __int64 v31; // r15
  unsigned __int64 v32; // r14
  __int64 i; // r13
  unsigned int v34; // ecx
  __int64 v35; // rax
  unsigned int v36; // [rsp+30h] [rbp-68h]
  __int64 v37; // [rsp+38h] [rbp-60h] BYREF
  _QWORD *v38; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int64 v39; // [rsp+48h] [rbp-50h]
  struct EventResource *v40; // [rsp+50h] [rbp-48h]
  _QWORD *v41; // [rsp+58h] [rbp-40h]
  PublisherManifestResource *v45; // [rsp+B8h] [rbp+20h] BYREF

  v45 = a4;
  v38 = 0;
  v9 = 0;
  v39 = 0;
  v10 = 0;
  *a8 = 0;
  *a9 = 0;
  *a7 = 0;
  v11 = *((_QWORD *)a4 + 4);
  v12 = 0;
  v13 = -1;
  if ( v11 )
  {
    v40 = (struct EventResource *)(v11 + 16);
    v14 = *(_DWORD *)(v11 + 8);
  }
  else
  {
    v40 = 0;
    v14 = 0;
  }
  v36 = v14;
  v15 = v14;
  v37 = v14;
  v17 = v14;
  v16 = 1072LL * v14;
  if ( !is_mul_ok(v17, 0x430u) )
    v16 = -1;
  v18 = __CFADD__(v16, 8);
  v19 = v16 + 8;
  if ( v18 )
    v19 = -1;
  try
  {
    v20 = operator new[](v19);
    v41 = v20;
    *v20 = v15;
    v21 = v20 + 1;
    `eh vector constructor iterator'(
      v20 + 1,
      0x430u,
      v36,
      (void (*)(void *))MANIFEST_DATA::MANIFEST_DATA,
      (void (*)(void *))MANIFEST_DATA::~MANIFEST_DATA);
    v38 = v21;
  }
  catch ( std::exception )
  {
    std::unique_ptr<MANIFEST_DATA [0]>::~unique_ptr<MANIFEST_DATA [0]>(&v38);
    return 8;
  }
  v20 = operator new[](v19);
  v41 = v20;
}

```

## disassembly

```asm
0x180009c7c  mov     rax, rsp
0x180009c7f  mov     [rax+20h], r9
0x180009c83  mov     [rax+18h], r8
0x180009c87  mov     [rax+10h], rdx
0x180009c8b  mov     [rax+8], ecx
0x180009c8e  push    rbx
0x180009c8f  push    rsi
0x180009c90  push    rdi
0x180009c91  push    r12
0x180009c93  push    r13
0x180009c95  push    r14
0x180009c97  push    r15
0x180009c99  sub     rsp, 60h
0x180009c9d  mov     rax, r9
0x180009ca0  xor     r10d, r10d
0x180009ca3  mov     [rsp+98h+var_58], r10
0x180009ca8  mov     edi, r10d
0x180009cab  mov     [rsp+98h+var_50], r10
0x180009cb0  mov     r12d, r10d
0x180009cb3  mov     r9, [rsp+98h+arg_38]
0x180009cbb  mov     [r9], r10
0x180009cbe  mov     rdx, [rsp+98h+arg_40]
0x180009cc6  mov     [rdx], r10d
0x180009cc9  mov     r8, [rsp+98h+arg_30]
0x180009cd1  mov     [r8], r10d
0x180009cd4  mov     rax, [rax+20h]
0x180009cd8  mov     r13d, 0FFFFFFFFh
0x180009cde  mov     esi, r10d
0x180009ce1  mov     r15d, r13d
0x180009ce4  test    rax, rax
0x180009ce7  jnz     short loc_180009CF3
0x180009ce9  mov     [rsp+98h+var_48], r10
0x180009cee  mov     eax, r10d
0x180009cf1  jmp     short loc_180009CFF
0x180009cf3  lea     rcx, [rax+10h]
0x180009cf7  mov     [rsp+98h+var_48], rcx
0x180009cfc  mov     eax, [rax+8]
0x180009cff  mov     dword ptr [rsp+98h+var_68], eax
0x180009d03  mov     ebx, eax
0x180009d05  mov     [rsp+98h+var_60], rbx
0x180009d0a  mov     eax, 430h
0x180009d0f  mul     rbx
0x180009d12  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180009d19  cmovb   rax, rcx
0x180009d1d  lea     r14d, [rcx+9]
0x180009d21  add     rax, r14
0x180009d24  cmovb   rax, rcx
0x180009d28  mov     rcx, rax; unsigned __int64
0x180009d2b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009d30  mov     [rsp+98h+var_40], rax
0x180009d35  mov     [rax], rbx
0x180009d38  lea     rbx, [rax+8]
0x180009d3c  lea     rax, ??1MANIFEST_DATA@@QEAA@XZ; MANIFEST_DATA::~MANIFEST_DATA(void)
0x180009d43  mov     [rsp+98h+var_78], rax; void (*)(void *)
0x180009d48  lea     r9, ??0MANIFEST_DATA@@QEAA@XZ; void (*)(void *)
0x180009d4f  mov     r8d, dword ptr [rsp+98h+var_68]; unsigned __int64
0x180009d54  mov     edx, 430h; unsigned __int64
0x180009d59  mov     rcx, rbx; void *
0x180009d5c  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180009d61  nop
0x180009d62  mov     [rsp+98h+var_58], rbx
0x180009d67  mov     eax, dword ptr [rsp+98h+var_68]
0x180009d6b  inc     r15d
0x180009d6e  cmp     r15d, eax
0x180009d71  jnb     loc_180009E3E
0x180009d77  test    r15d, r15d
0x180009d7a  jnz     short loc_180009D83
0x180009d7c  mov     rsi, [rsp+98h+var_48]
0x180009d81  jmp     short loc_180009D87
0x180009d83  add     rsi, 30h ; '0'
0x180009d87  mov     cl, [rsp+98h+arg_28]
0x180009d8e  cmp     cl, [rsi+2]
0x180009d91  jnz     short loc_180009D6B
0x180009d93  mov     eax, r12d
0x180009d96  imul    rdi, rax, 430h
0x180009d9d  add     rdi, rbx
0x180009da0  lea     r8, [rdi+3D8h]; struct EventResourceData *
0x180009da7  mov     rdx, rsi; struct EventResource *
0x180009daa  mov     rcx, [rsp+98h+arg_18]; this
0x180009db2  call    ?GetEventResource@PublisherManifestResource@@QEBAKPEBUEventResource@@AEAUEventResourceData@@@Z; PublisherManifestResource::GetEventResource(EventResource const *,EventResourceData &)
0x180009db7  test    eax, eax
0x180009db9  jnz     loc_180009F6F
0x180009dbf  mov     dword ptr [rsp+98h+var_60], eax
0x180009dc3  lea     rax, [rsp+98h+var_60]
0x180009dc8  mov     [rsp+98h+var_70], rax
0x180009dcd  mov     [rsp+98h+var_78], rdi
0x180009dd2  mov     r9, [rsp+98h+arg_10]
0x180009dda  lea     r8, [rdi+3D8h]
0x180009de1  mov     rdx, [rsp+98h+arg_18]
0x180009de9  mov     rcx, [rsp+98h+arg_8]
0x180009df1  call    GetTraceEventInfoManifest
0x180009df6  mov     edi, eax
0x180009df8  test    eax, eax
0x180009dfa  jnz     loc_180009FAB
0x180009e00  mov     eax, dword ptr [rsp+98h+var_60]
0x180009e04  lea     ecx, [rax+7]
0x180009e07  cmp     ecx, eax
0x180009e09  jb      short loc_180009E10
0x180009e0b  and     ecx, 0FFFFFFF8h
0x180009e0e  jmp     short loc_180009E13
0x180009e10  mov     ecx, r13d
0x180009e13  mov     dword ptr [rsp+98h+var_60], ecx
0x180009e17  mov     edi, ecx
0x180009e19  add     rdi, [rsp+98h+var_50]
0x180009e1e  cmp     rdi, [rsp+98h+var_50]
0x180009e23  jb      short loc_180009E32
0x180009e25  mov     [rsp+98h+var_50], rdi
0x180009e2a  inc     r12d
0x180009e2d  jmp     loc_180009D67
0x180009e32  lea     rcx, [rsp+98h+var_58]
0x180009e37  call    ??1?$unique_ptr@$$BY0A@VMANIFEST_DATA@@U?$default_delete@$$BY0A@VMANIFEST_DATA@@@std@@@std@@QEAA@XZ; std::unique_ptr<MANIFEST_DATA [0]>::~unique_ptr<MANIFEST_DATA [0]>(void)
0x180009e3c  jmp     short loc_180009E6B
0x180009e3e  test    r12d, r12d
0x180009e41  jz      loc_180009FB9
0x180009e47  mov     [rsp+98h+arg_18], 0
0x180009e53  mov     eax, r12d
0x180009e56  mul     r14
0x180009e59  test    rdx, rdx
0x180009e5c  jz      short loc_180009E75
0x180009e5e  test    rbx, rbx
0x180009e61  jz      short loc_180009E6B
0x180009e63  mov     rdx, rbx
0x180009e66  call    ??$?RVMANIFEST_DATA@@$0A@@?$default_delete@$$BY0A@VMANIFEST_DATA@@@std@@QEBAXPEAVMANIFEST_DATA@@@Z; std::default_delete<MANIFEST_DATA [0]>::operator()<MANIFEST_DATA,0>(MANIFEST_DATA *)
0x180009e6b  mov     eax, 216h
0x180009e70  jmp     loc_180009FD9
0x180009e75  add     rdi, rax
0x180009e78  cmp     rdi, [rsp+98h+var_50]
0x180009e7d  jb      loc_180009FA6
0x180009e83  mov     rdx, [rsp+98h+arg_40]; unsigned int *
0x180009e8b  mov     rcx, rdi; unsigned __int64
0x180009e8e  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180009e93  test    eax, eax
0x180009e95  js      loc_180009FA6
0x180009e9b  cmp     rdi, r13
0x180009e9e  jnb     loc_180009FA1
0x180009ea4  call    cs:__imp_GetProcessHeap
0x180009eaa  mov     r8, rdi; dwBytes
0x180009ead  mov     edx, r14d; dwFlags
0x180009eb0  mov     rcx, rax; hHeap
0x180009eb3  call    cs:__imp_HeapAlloc
0x180009eb9  mov     rsi, rax
0x180009ebc  test    rax, rax
0x180009ebf  jz      loc_180009FA1
0x180009ec5  xor     r15d, r15d
0x180009ec8  mov     eax, r12d
0x180009ecb  lea     r14, [rsi+rax*8]
0x180009ecf  xor     r13d, r13d
0x180009ed2  lea     rax, [rsi+rdi]
0x180009ed6  cmp     r13d, r12d
0x180009ed9  jnb     loc_180009F7A
0x180009edf  cmp     r14, rax
0x180009ee2  jnb     loc_180009F73
0x180009ee8  cmp     r15, rdi
0x180009eeb  jnb     loc_180009F73
0x180009ef1  mov     dword ptr [rsp+98h+arg_18], 0
0x180009efc  mov     ecx, r13d
0x180009eff  mov     eax, edi
0x180009f01  sub     eax, r15d
0x180009f04  imul    rdx, rcx, 430h
0x180009f0b  add     rdx, rbx
0x180009f0e  lea     rcx, [rsp+98h+arg_18]
0x180009f16  mov     [rsp+98h+var_70], rcx
0x180009f1b  mov     dword ptr [rsp+98h+var_78], eax
0x180009f1f  mov     r9, r14
0x180009f22  mov     r8, [rsp+98h+arg_20]
0x180009f2a  mov     ecx, [rsp+98h+arg_0]
0x180009f31  call    CopyManifestDataToTraceEventInfo
0x180009f36  test    eax, eax
0x180009f38  jnz     short loc_180009F6F
0x180009f3a  mov     eax, dword ptr [rsp+98h+arg_18]
0x180009f41  lea     ecx, [rax+7]
0x180009f44  cmp     ecx, eax
0x180009f46  jb      short loc_180009F4D
0x180009f48  and     ecx, 0FFFFFFF8h
0x180009f4b  jmp     short loc_180009F52
0x180009f4d  mov     ecx, 0FFFFFFFFh
0x180009f52  mov     eax, ecx
0x180009f54  lea     rcx, [rax+r15]
0x180009f58  cmp     rcx, r15
0x180009f5b  jb      short loc_180009FA6
0x180009f5d  mov     r15, rcx
0x180009f60  mov     [rsi+r13*8], r14
0x180009f64  add     r14, rax
0x180009f67  inc     r13d
0x180009f6a  jmp     loc_180009ED2
0x180009f6f  mov     edi, eax
0x180009f71  jmp     short loc_180009FAB
0x180009f73  mov     edi, 6Fh ; 'o'
0x180009f78  jmp     short loc_180009FAB
0x180009f7a  mov     rax, [rsp+98h+arg_38]
0x180009f82  mov     [rax], rsi
0x180009f85  mov     rax, [rsp+98h+arg_30]
0x180009f8d  mov     [rax], r12d
0x180009f90  test    rbx, rbx
0x180009f93  jz      short loc_180009F9D
0x180009f95  mov     rdx, rbx
0x180009f98  call    ??$?RVMANIFEST_DATA@@$0A@@?$default_delete@$$BY0A@VMANIFEST_DATA@@@std@@QEBAXPEAVMANIFEST_DATA@@@Z; std::default_delete<MANIFEST_DATA [0]>::operator()<MANIFEST_DATA,0>(MANIFEST_DATA *)
0x180009f9d  xor     eax, eax
0x180009f9f  jmp     short loc_180009FD9
0x180009fa1  mov     edi, r14d
0x180009fa4  jmp     short loc_180009FAB
0x180009fa6  mov     edi, 216h
0x180009fab  lea     rcx, [rsp+98h+var_58]
0x180009fb0  call    ??1?$unique_ptr@$$BY0A@VMANIFEST_DATA@@U?$default_delete@$$BY0A@VMANIFEST_DATA@@@std@@@std@@QEAA@XZ; std::unique_ptr<MANIFEST_DATA [0]>::~unique_ptr<MANIFEST_DATA [0]>(void)
0x180009fb5  mov     eax, edi
0x180009fb7  jmp     short loc_180009FD9
0x180009fb9  lea     rcx, [rsp+98h+var_58]
0x180009fbe  call    ??1?$unique_ptr@$$BY0A@VMANIFEST_DATA@@U?$default_delete@$$BY0A@VMANIFEST_DATA@@@std@@@std@@QEAA@XZ; std::unique_ptr<MANIFEST_DATA [0]>::~unique_ptr<MANIFEST_DATA [0]>(void)
0x180009fc3  mov     eax, 0C007FF01h
0x180009fc8  jmp     short loc_180009FD9
0x180009fca  lea     rcx, [rsp+98h+var_58]
0x180009fcf  call    ??1?$unique_ptr@$$BY0A@VMANIFEST_DATA@@U?$default_delete@$$BY0A@VMANIFEST_DATA@@@std@@@std@@QEAA@XZ; std::unique_ptr<MANIFEST_DATA [0]>::~unique_ptr<MANIFEST_DATA [0]>(void)
0x180009fd4  mov     eax, 8
0x180009fd9  add     rsp, 60h
0x180009fdd  pop     r15
0x180009fdf  pop     r14
0x180009fe1  pop     r13
0x180009fe3  pop     r12
0x180009fe5  pop     rdi
0x180009fe6  pop     rsi
0x180009fe7  pop     rbx
0x180009fe8  retn
```
