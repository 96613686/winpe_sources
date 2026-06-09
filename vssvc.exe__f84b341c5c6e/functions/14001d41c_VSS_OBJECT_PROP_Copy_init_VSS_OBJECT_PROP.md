# VSS_OBJECT_PROP_Copy::init(_VSS_OBJECT_PROP *)

- ea: `0x14001d41c`
- end: `0x14001d696`
- name: `?init@VSS_OBJECT_PROP_Copy@@SAXPEAU_VSS_OBJECT_PROP@@@Z`
- size: `634`
- prototype: `void __fastcall(struct _VSS_OBJECT_PROP *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14001b804`
- `0x14001e49c`

## callees

- `0x1400137c0`
- `0x140013cb0`
- `0x14001d41c`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001d4d8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001d4d8`
- `VssTrace!__imp_VssTraceMessage` at `0x14001d662`
- `VssTrace!__imp_VssTraceMessage` at `0x14001d662`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001d5ea`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001d5ea`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001d536`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001d536`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d5d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d5d1`

## string_xrefs

- `0x14001d42e`: `base\stor\vss\modules\prop\copy.cxx`
- `0x14001d44a`: `PRPCOPYC`
- `0x14001d43c`: `VSS_OBJECT_PROP_Copy::init`

## pseudocode

```c
void __fastcall VSS_OBJECT_PROP_Copy::init(struct _VSS_OBJECT_PROP *a1)
{
  __int64 v2; // rcx
  int v3; // ebx
  __int64 i; // rbx
  void *v5; // rcx
  int v6; // eax
  unsigned __int64 v7; // [rsp+50h] [rbp-138h] BYREF
  int v8; // [rsp+58h] [rbp-130h]
  const unsigned __int16 *v9; // [rsp+60h] [rbp-128h]
  const unsigned __int16 *v10; // [rsp+68h] [rbp-120h]
  unsigned int v11; // [rsp+70h] [rbp-118h]
  int v12; // [rsp+74h] [rbp-114h]
  const unsigned __int16 *v13; // [rsp+78h] [rbp-110h]
  unsigned int v14; // [rsp+80h] [rbp-108h]
  DWORD TickCount; // [rsp+84h] [rbp-104h]
  int v16; // [rsp+88h] [rbp-100h]
  __int128 v17; // [rsp+90h] [rbp-F8h]
  __int128 v18; // [rsp+A0h] [rbp-E8h]
  __int64 v19; // [rsp+B0h] [rbp-D8h]
  const unsigned __int16 *v20; // [rsp+D8h] [rbp-B0h]
  const unsigned __int16 *v21; // [rsp+E0h] [rbp-A8h]
  const unsigned __int16 *v22; // [rsp+E8h] [rbp-A0h]
  int v23; // [rsp+F0h] [rbp-98h]
  int v24; // [rsp+F4h] [rbp-94h]
  int v25; // [rsp+F8h] [rbp-90h]
  LPVOID pv[15]; // [rsp+100h] [rbp-88h] BYREF
  int v27; // [rsp+178h] [rbp-10h]
  __int64 v28; // [rsp+190h] [rbp+8h] BYREF

  v20 = L"base\\stor\\vss\\modules\\prop\\copy.cxx";
  v21 = L"VSS_OBJECT_PROP_Copy::init";
  v22 = L"PRPCOPYC";
  v23 = 165;
  v24 = 11;
  v25 = 255;
  v27 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v8 = 0;
  v13 = L"VSS_OBJECT_PROP_Copy::init";
  v9 = L"base\\stor\\vss\\modules\\prop\\copy.cxx";
  v10 = L"PRPCOPYC";
  v11 = 165;
  v12 = 11;
  TickCount = GetTickCount();
  v16 = 255;
  v7 = 0xFFFFFFFF00000000uLL;
  v19 = 0;
  v17 = 0;
  v18 = 0;
  v28 = 0;
  if ( (int)VssGetTracingContextPerThread(&v28) >= 0 )
  {
    v6 = VssSetTracingContextPerThread(&v7);
    v2 = v19;
    if ( v6 >= 0 )
      v2 = v28;
    v19 = v2;
  }
  else
  {
    v2 = v19;
  }
  if ( v2 )
    v14 = *(_DWORD *)(v2 + 48) + 1;
  else
    v14 = 0;
  v3 = 160;
  if ( v16 != 255 )
    v3 = v16;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v7) )
    VssTraceMessage(v9, v10, v11, v14, v12, v13, L"ENTER", v3, 0);
  if ( HIBYTE(v27) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v5 = pv[i];
      if ( v5 )
      {
        CoTaskMemFree(v5);
        pv[i] = 0;
      }
    }
  }
  if ( a1 )
    memset_0(a1, 0, sizeof(struct _VSS_OBJECT_PROP));
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v7);
}

```

## disassembly

```asm
0x14001d41c  mov     r11, rsp
0x14001d41f  mov     [r11+10h], rbx
0x14001d423  push    rdi
0x14001d424  sub     rsp, 180h
0x14001d42b  mov     rdi, rcx
0x14001d42e  lea     rax, aBaseStorVssMod_32; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x14001d435  mov     [r11-0B0h], rax
0x14001d43c  lea     rax, aVssObjectPropC_0; "VSS_OBJECT_PROP_Copy::init"
0x14001d443  mov     [r11-0A8h], rax
0x14001d44a  lea     rax, aPrpcopyc; "PRPCOPYC"
0x14001d451  mov     [r11-0A0h], rax
0x14001d458  mov     [rsp+188h+var_98], 0A5h
0x14001d463  mov     [rsp+188h+var_94], 0Bh
0x14001d46e  mov     [rsp+188h+var_90], 0FFh
0x14001d479  mov     dword ptr [r11-10h], 1000000h
0x14001d481  xor     edx, edx; Val
0x14001d483  lea     r8d, [rdx+78h]; Size
0x14001d487  lea     rcx, [r11-88h]; void *
0x14001d48e  call    memset_0
0x14001d493  mov     [rsp+188h+var_130], 0
0x14001d49b  mov     rax, [rsp+188h+var_A8]
0x14001d4a3  mov     [rsp+188h+var_110], rax
0x14001d4a8  mov     rax, [rsp+188h+var_B0]
0x14001d4b0  mov     [rsp+188h+var_128], rax
0x14001d4b5  mov     rax, [rsp+188h+var_A0]
0x14001d4bd  mov     [rsp+188h+var_120], rax
0x14001d4c2  mov     eax, [rsp+188h+var_98]
0x14001d4c9  mov     [rsp+188h+var_118], eax
0x14001d4cd  mov     eax, [rsp+188h+var_94]
0x14001d4d4  mov     [rsp+188h+var_114], eax
0x14001d4d8  call    cs:__imp_GetTickCount
0x14001d4de  mov     [rsp+188h+var_104], eax
0x14001d4e5  mov     [rsp+188h+var_134], 0FFFFFFFFh
0x14001d4ed  mov     eax, [rsp+188h+var_90]
0x14001d4f4  mov     [rsp+188h+var_100], eax
0x14001d4fb  mov     [rsp+188h+var_138], 0
0x14001d503  mov     [rsp+188h+var_D8], 0
0x14001d50f  xorps   xmm0, xmm0
0x14001d512  movups  [rsp+188h+var_F8], xmm0
0x14001d51a  movups  [rsp+188h+var_E8], xmm0
0x14001d522  mov     [rsp+188h+arg_0], 0
0x14001d52e  lea     rcx, [rsp+188h+arg_0]
0x14001d536  call    cs:__imp_VssGetTracingContextPerThread
0x14001d53c  test    eax, eax
0x14001d53e  jns     loc_14001D5E5
0x14001d544  mov     rcx, [rsp+188h+var_D8]
0x14001d54c  test    rcx, rcx
0x14001d54f  jz      loc_14001D610
0x14001d555  mov     eax, [rcx+30h]
0x14001d558  inc     eax
0x14001d55a  mov     [rsp+188h+var_108], eax
0x14001d561  mov     ebx, 0A0h
0x14001d566  cmp     [rsp+188h+var_100], 0FFh
0x14001d571  cmovnz  ebx, [rsp+188h+var_100]
0x14001d579  lea     rcx, [rsp+188h+var_138]; this
0x14001d57e  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14001d583  test    eax, eax
0x14001d585  jnz     loc_14001D620
0x14001d58b  cmp     [rsp+188h+var_D], 0
0x14001d593  jz      short loc_14001D5AD
0x14001d595  xor     ebx, ebx
0x14001d597  mov     rcx, [rsp+rbx*8+188h+pv]; pv
0x14001d59f  test    rcx, rcx
0x14001d5a2  jnz     short loc_14001D5D1
0x14001d5a4  inc     rbx
0x14001d5a7  cmp     rbx, 0Fh
0x14001d5ab  jnz     short loc_14001D597
0x14001d5ad  test    rdi, rdi
0x14001d5b0  jnz     loc_14001D66D
0x14001d5b6  lea     rcx, [rsp+188h+var_138]; this
0x14001d5bb  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14001d5c0  mov     rbx, [rsp+188h+arg_8]
0x14001d5c8  add     rsp, 180h
0x14001d5cf  pop     rdi
0x14001d5d0  retn
0x14001d5d1  call    cs:__imp_CoTaskMemFree
0x14001d5d7  mov     [rsp+rbx*8+188h+pv], 0
0x14001d5e3  jmp     short loc_14001D5A4
0x14001d5e5  lea     rcx, [rsp+188h+var_138]
0x14001d5ea  call    cs:__imp_VssSetTracingContextPerThread
0x14001d5f0  mov     rcx, [rsp+188h+var_D8]
0x14001d5f8  test    eax, eax
0x14001d5fa  cmovns  rcx, [rsp+188h+arg_0]
0x14001d603  mov     [rsp+188h+var_D8], rcx
0x14001d60b  jmp     loc_14001D54C
0x14001d610  mov     [rsp+188h+var_108], 0
0x14001d61b  jmp     loc_14001D561
0x14001d620  mov     [rsp+188h+var_148], 0
0x14001d629  mov     [rsp+188h+var_150], ebx
0x14001d62d  lea     rax, aEnter; "ENTER"
0x14001d634  mov     [rsp+188h+var_158], rax
0x14001d639  mov     rax, [rsp+188h+var_110]
0x14001d63e  mov     [rsp+188h+var_160], rax
0x14001d643  mov     eax, [rsp+188h+var_114]
0x14001d647  mov     [rsp+188h+var_168], eax
0x14001d64b  mov     r9d, [rsp+188h+var_108]
0x14001d653  mov     r8d, [rsp+188h+var_118]
0x14001d658  mov     rdx, [rsp+188h+var_120]
0x14001d65d  mov     rcx, [rsp+188h+var_128]
0x14001d662  call    cs:__imp_VssTraceMessage
0x14001d668  jmp     loc_14001D58B
0x14001d66d  xor     edx, edx; Val
0x14001d66f  mov     r8d, 88h; Size
0x14001d675  mov     rcx, rdi; void *
0x14001d678  call    memset_0
0x14001d67d  jmp     loc_14001D5B6
0x14001d682  jmp     loc_14001D5B6
0x14001d687  jmp     loc_14001D5B6
0x14001d68c  jmp     loc_14001D5B6
0x14001d691  jmp     loc_14001D5B6
```
