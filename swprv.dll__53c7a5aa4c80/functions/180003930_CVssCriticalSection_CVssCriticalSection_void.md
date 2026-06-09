# CVssCriticalSection::~CVssCriticalSection(void)

- ea: `0x180003930`
- end: `0x1800039d2`
- name: `??1CVssCriticalSection@@QEAA@XZ`
- size: `162`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800037b0`
- `0x18001d8dc`
- `0x18004ae30`

## callees

- `0x18000212c`
- `0x180003930`
- `0x180033a8c`
- `0x180033c78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800039b2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800039b2`

## pseudocode

```c
void __fastcall CVssCriticalSection::~CVssCriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  _QWORD v2[3]; // [rsp+20h] [rbp-E0h] BYREF
  int v3; // [rsp+38h] [rbp-C8h]
  int v4; // [rsp+3Ch] [rbp-C4h]
  int v5; // [rsp+40h] [rbp-C0h]
  _BYTE v6[120]; // [rsp+48h] [rbp-B8h] BYREF
  int v7; // [rsp+C0h] [rbp-40h]
  _BYTE v8[112]; // [rsp+D0h] [rbp-30h] BYREF

  v3 = 185;
  v2[0] = L"base\\stor\\vss\\inc\\vs_types.hxx";
  v4 = 11;
  v2[1] = L"CVssCriticalSection::~CVssCriticalSection";
  v5 = 255;
  v2[2] = L"INCTYPEH";
  v7 = 0x1000000;
  memset_0(v6, 0, sizeof(v6));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v8, (__int64)v2, 0);
  if ( LOBYTE(lpCriticalSection[1].DebugInfo) )
    DeleteCriticalSection(lpCriticalSection);
  CVssFunctionTracer::~CVssFunctionTracer((CVssFunctionTracer *)v8);
}

```

## disassembly

```asm
0x180003930  mov     [rsp-8+arg_0], rbx
0x180003935  push    rbp
0x180003936  lea     rbp, [rsp-40h]
0x18000393b  sub     rsp, 140h
0x180003942  lea     rax, aBaseStorVssInc_3; "base\\stor\\vss\\inc\\vs_types.hxx"
0x180003949  mov     [rsp+140h+var_108], 0B9h
0x180003951  mov     [rsp+140h+var_120], rax
0x180003956  xor     edx, edx; Val
0x180003958  lea     rax, aCvsscriticalse; "CVssCriticalSection::~CVssCriticalSecti"...
0x18000395f  mov     [rsp+140h+var_104], 0Bh
0x180003967  mov     [rsp+140h+var_118], rax
0x18000396c  mov     rbx, rcx
0x18000396f  lea     rax, aInctypeh; "INCTYPEH"
0x180003976  mov     [rsp+140h+var_100], 0FFh
0x18000397e  lea     r8d, [rdx+78h]; Size
0x180003982  mov     [rsp+140h+var_110], rax
0x180003987  lea     rcx, [rsp+140h+var_F8]; void *
0x18000398c  mov     [rbp+40h+var_80], 1000000h
0x180003993  call    memset_0
0x180003998  xor     r8d, r8d
0x18000399b  lea     rdx, [rsp+140h+var_120]
0x1800039a0  lea     rcx, [rbp+40h+var_70]
0x1800039a4  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1800039a9  cmp     byte ptr [rbx+28h], 0
0x1800039ad  jz      short loc_1800039B8
0x1800039af  mov     rcx, rbx; lpCriticalSection
0x1800039b2  call    cs:__imp_DeleteCriticalSection
0x1800039b8  lea     rcx, [rbp+40h+var_70]; this
0x1800039bc  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1800039c1  mov     rbx, [rsp+140h+arg_0]
0x1800039c9  add     rsp, 140h
0x1800039d0  pop     rbp
0x1800039d1  retn
```
