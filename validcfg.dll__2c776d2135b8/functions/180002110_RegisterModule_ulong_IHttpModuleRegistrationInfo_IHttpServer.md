# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180002110`
- end: `0x180002261`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(__int64, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callees

- `0x1800017e0`
- `0x180001820`
- `0x180002110`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  _QWORD *v5; // rbx
  __int64 v6; // rax
  int v7; // edi
  _QWORD *v8; // rax
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  v10 = 0;
  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  v5 = 0;
  g_pDetectISAPIConfigModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  v6 = *(_QWORD *)a3;
  g_pHttpServer = a3;
  v7 = (*(__int64 (__fastcall **)(struct IHttpServer *, __int64 *))(v6 + 160))(a3, &v10);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v10 + 16LL))(
           v10,
           4,
           &g_dwPipelineMode);
    if ( v7 >= 0 && !g_dwPipelineMode )
    {
      v5 = operator new(0x10u);
      if ( !v5 )
      {
        v7 = -2147024888;
LABEL_14:
        v5 = 0;
        goto LABEL_15;
      }
      v5[1] = 0;
      *v5 = &CDetectISAPIConfigModuleFactory::`vftable';
      v8 = operator new(8u);
      if ( v8 )
        *v8 = &CDetectISAPIConfigModule::`vftable';
      v5[1] = v8;
      if ( v8 )
      {
        v7 = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64))(*(_QWORD *)a2 + 16LL))(
               a2,
               v5,
               1);
        if ( v7 >= 0 )
          goto LABEL_14;
      }
      else
      {
        v7 = -2147024888;
      }
    }
  }
LABEL_15:
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
    v10 = 0;
  }
  if ( v5 )
    operator delete(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180002110  mov     [rsp+arg_0], rbx
0x180002115  mov     [rsp+arg_10], rsi
0x18000211a  push    rdi
0x18000211b  sub     rsp, 30h
0x18000211f  mov     [rsp+38h+arg_8], 0
0x180002128  mov     rdi, r8
0x18000212b  mov     rsi, rdx
0x18000212e  test    rdx, rdx
0x180002131  jz      loc_18000224A
0x180002137  test    r8, r8
0x18000213a  jz      loc_18000224A
0x180002140  mov     rax, [rdx]
0x180002143  mov     rcx, rdx
0x180002146  xor     ebx, ebx
0x180002148  mov     rax, [rax+8]
0x18000214c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002151  mov     cs:?g_pDetectISAPIConfigModuleContext@@3PEAXEA, rax; void * g_pDetectISAPIConfigModuleContext
0x180002158  lea     rdx, [rsp+38h+arg_8]
0x18000215d  mov     rax, [rdi]
0x180002160  mov     rcx, rdi
0x180002163  mov     cs:?g_pHttpServer@@3PEAVIHttpServer@@EA, rdi; IHttpServer * g_pHttpServer
0x18000216a  mov     rax, [rax+0A0h]
0x180002171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002176  mov     edi, eax
0x180002178  test    eax, eax
0x18000217a  js      loc_18000221C
0x180002180  mov     rcx, [rsp+38h+arg_8]
0x180002185  lea     r8, ?g_dwPipelineMode@@3KA; ulong g_dwPipelineMode
0x18000218c  lea     edx, [rbx+4]
0x18000218f  mov     rax, [rcx]
0x180002192  mov     rax, [rax+10h]
0x180002196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000219b  mov     edi, eax
0x18000219d  test    eax, eax
0x18000219f  js      short loc_18000221C
0x1800021a1  cmp     cs:?g_dwPipelineMode@@3KA, ebx; ulong g_dwPipelineMode
0x1800021a7  jnz     short loc_18000221C
0x1800021a9  lea     ecx, [rbx+10h]; Size
0x1800021ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800021b1  mov     rbx, rax
0x1800021b4  test    rax, rax
0x1800021b7  jz      short loc_180002215
0x1800021b9  lea     rax, ??_7CDetectISAPIConfigModuleFactory@@6B@; const CDetectISAPIConfigModuleFactory::`vftable'
0x1800021c0  mov     qword ptr [rbx+8], 0
0x1800021c8  mov     ecx, 8; Size
0x1800021cd  mov     [rbx], rax
0x1800021d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800021d5  test    rax, rax
0x1800021d8  jz      short loc_1800021E4
0x1800021da  lea     rcx, ??_7CDetectISAPIConfigModule@@6B@; const CDetectISAPIConfigModule::`vftable'
0x1800021e1  mov     [rax], rcx
0x1800021e4  mov     [rbx+8], rax
0x1800021e8  test    rax, rax
0x1800021eb  jz      short loc_18000220E
0x1800021ed  mov     rax, [rsi]
0x1800021f0  xor     r9d, r9d
0x1800021f3  mov     rdx, rbx
0x1800021f6  mov     rcx, rsi
0x1800021f9  mov     rax, [rax+10h]
0x1800021fd  lea     r8d, [r9+1]
0x180002201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002206  mov     edi, eax
0x180002208  test    eax, eax
0x18000220a  js      short loc_18000221C
0x18000220c  jmp     short loc_18000221A
0x18000220e  mov     edi, 80070008h
0x180002213  jmp     short loc_18000221C
0x180002215  mov     edi, 80070008h
0x18000221a  xor     ebx, ebx
0x18000221c  mov     rcx, [rsp+38h+arg_8]
0x180002221  test    rcx, rcx
0x180002224  jz      short loc_18000223B
0x180002226  mov     rax, [rcx]
0x180002229  mov     rax, [rax+8]
0x18000222d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002232  mov     [rsp+38h+arg_8], 0
0x18000223b  test    rbx, rbx
0x18000223e  jz      short loc_18000224F
0x180002240  mov     rcx, rbx; Block
0x180002243  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002248  jmp     short loc_18000224F
0x18000224a  mov     edi, 80070057h
0x18000224f  mov     rbx, [rsp+38h+arg_0]
0x180002254  mov     eax, edi
0x180002256  mov     rsi, [rsp+38h+arg_10]
0x18000225b  add     rsp, 30h
0x18000225f  pop     rdi
0x180002260  retn
```
