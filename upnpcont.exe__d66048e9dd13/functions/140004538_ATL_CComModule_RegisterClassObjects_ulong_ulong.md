# ATL::CComModule::RegisterClassObjects(ulong,ulong)

- ea: `0x140004538`
- end: `0x140004690`
- name: `?RegisterClassObjects@CComModule@ATL@@QEAAJKK@Z`
- size: `344`
- prototype: `__int64 __fastcall(IUnknown *this, __int64, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005c80`

## callees

- `0x140004538`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1400045ae`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140004653`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1400045ae`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140004653`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::RegisterClassObjects(IUnknown *this, __int64 a2, DWORD a3)
{
  __int64 v3; // rdi
  HRESULT v5; // ebx
  __int64 (__fastcall *v6)(_QWORD, GUID *, LPUNKNOWN *); // rax
  __int64 *v7; // rdi
  __int64 *v8; // rax
  __int64 v9; // rsi
  bool v10; // zf
  LPUNKNOWN pUnk; // [rsp+60h] [rbp+8h] BYREF

  pUnk = this;
  v3 = qword_14000B378;
  if ( qword_14000B378 && (v5 = 0, *(_QWORD *)qword_14000B378) )
  {
    while ( !v5 )
    {
      v6 = *(__int64 (__fastcall **)(_QWORD, GUID *, LPUNKNOWN *))(v3 + 16);
      pUnk = 0;
      if ( v6 )
      {
        v5 = v6(*(_QWORD *)(v3 + 24), &GUID_00000000_0000_0000_c000_000000000046, &pUnk);
        if ( v5 >= 0 )
          v5 = CoRegisterClassObject(*(const IID *const *)v3, pUnk, 4u, a3, (LPDWORD)(v3 + 40));
        if ( pUnk )
          ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
      }
      v3 += 72;
      if ( !*(_QWORD *)v3 )
      {
        if ( v5 )
          return (unsigned int)v5;
        goto LABEL_11;
      }
    }
  }
  else
  {
LABEL_11:
    v7 = off_14000B0B0[0];
    v5 = 1;
    v8 = off_14000B0B8;
    while ( v7 < v8 && v5 >= 0 )
    {
      v9 = *v7;
      if ( *v7 )
      {
        v10 = *(_QWORD *)(v9 + 16) == 0;
        pUnk = 0;
        if ( v10 )
        {
          v5 = 0;
        }
        else
        {
          v5 = (*(__int64 (__fastcall **)(_QWORD, GUID *, LPUNKNOWN *))(v9 + 16))(
                 *(_QWORD *)(v9 + 24),
                 &GUID_00000000_0000_0000_c000_000000000046,
                 &pUnk);
          if ( v5 >= 0 )
            v5 = CoRegisterClassObject(*(const IID *const *)v9, pUnk, 4u, a3, (LPDWORD)(v9 + 40));
          if ( pUnk )
            ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
          v8 = off_14000B0B8;
        }
      }
      ++v7;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140004538  mov     [rsp+pUnk], rcx
0x14000453d  push    rbx
0x14000453e  push    rbp
0x14000453f  push    rsi
0x140004540  push    rdi
0x140004541  sub     rsp, 38h
0x140004545  mov     rdi, cs:qword_14000B378
0x14000454c  mov     ebp, r8d
0x14000454f  test    rdi, rdi
0x140004552  jz      loc_1400045DE
0x140004558  xor     ebx, ebx
0x14000455a  cmp     [rdi], rbx
0x14000455d  jz      short loc_1400045DE
0x14000455f  test    ebx, ebx
0x140004561  jnz     loc_140004685
0x140004567  mov     rax, [rdi+10h]
0x14000456b  mov     [rsp+58h+pUnk], 0
0x140004574  test    rax, rax
0x140004577  jz      short loc_1400045CC
0x140004579  mov     rcx, [rdi+18h]
0x14000457d  lea     r8, [rsp+58h+pUnk]
0x140004582  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140004589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000458e  mov     ebx, eax
0x140004590  test    eax, eax
0x140004592  js      short loc_1400045B6
0x140004594  mov     rdx, [rsp+58h+pUnk]; pUnk
0x140004599  lea     rax, [rdi+28h]
0x14000459d  mov     rcx, [rdi]; rclsid
0x1400045a0  mov     r9d, ebp; flags
0x1400045a3  mov     r8d, 4; dwClsContext
0x1400045a9  mov     [rsp+58h+lpdwRegister], rax; lpdwRegister
0x1400045ae  call    cs:__imp_CoRegisterClassObject
0x1400045b4  mov     ebx, eax
0x1400045b6  mov     rcx, [rsp+58h+pUnk]
0x1400045bb  test    rcx, rcx
0x1400045be  jz      short loc_1400045CC
0x1400045c0  mov     rax, [rcx]
0x1400045c3  mov     rax, [rax+10h]
0x1400045c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045cc  add     rdi, 48h ; 'H'
0x1400045d0  cmp     qword ptr [rdi], 0
0x1400045d4  jnz     short loc_14000455F
0x1400045d6  test    ebx, ebx
0x1400045d8  jnz     loc_140004685
0x1400045de  mov     rdi, cs:off_14000B0B0
0x1400045e5  mov     ebx, 1
0x1400045ea  mov     rax, cs:off_14000B0B8
0x1400045f1  jmp     loc_14000467C
0x1400045f6  test    ebx, ebx
0x1400045f8  js      loc_140004685
0x1400045fe  mov     rsi, [rdi]
0x140004601  test    rsi, rsi
0x140004604  jz      short loc_140004678
0x140004606  cmp     qword ptr [rsi+10h], 0
0x14000460b  mov     [rsp+58h+pUnk], 0
0x140004614  jnz     short loc_14000461A
0x140004616  xor     ebx, ebx
0x140004618  jmp     short loc_140004678
0x14000461a  mov     rcx, [rsi+18h]
0x14000461e  lea     r8, [rsp+58h+pUnk]
0x140004623  mov     rax, [rsi+10h]
0x140004627  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x14000462e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004633  mov     ebx, eax
0x140004635  test    eax, eax
0x140004637  js      short loc_14000465B
0x140004639  mov     rdx, [rsp+58h+pUnk]; pUnk
0x14000463e  lea     rax, [rsi+28h]
0x140004642  mov     rcx, [rsi]; rclsid
0x140004645  mov     r9d, ebp; flags
0x140004648  mov     r8d, 4; dwClsContext
0x14000464e  mov     [rsp+58h+lpdwRegister], rax; lpdwRegister
0x140004653  call    cs:__imp_CoRegisterClassObject
0x140004659  mov     ebx, eax
0x14000465b  mov     rcx, [rsp+58h+pUnk]
0x140004660  test    rcx, rcx
0x140004663  jz      short loc_140004671
0x140004665  mov     rax, [rcx]
0x140004668  mov     rax, [rax+10h]
0x14000466c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004671  mov     rax, cs:off_14000B0B8
0x140004678  add     rdi, 8
0x14000467c  cmp     rdi, rax
0x14000467f  jb      loc_1400045F6
0x140004685  mov     eax, ebx
0x140004687  add     rsp, 38h
0x14000468b  pop     rdi
0x14000468c  pop     rsi
0x14000468d  pop     rbp
0x14000468e  pop     rbx
0x14000468f  retn
```
