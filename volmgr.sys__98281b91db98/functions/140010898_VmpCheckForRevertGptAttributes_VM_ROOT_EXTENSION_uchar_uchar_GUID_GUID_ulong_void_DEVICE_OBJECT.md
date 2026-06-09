# VmpCheckForRevertGptAttributes(VM_ROOT_EXTENSION *,uchar,uchar,_GUID *,_GUID *,ulong,void *,_DEVICE_OBJECT *)

- ea: `0x140010898`
- end: `0x1400109ce`
- name: `?VmpCheckForRevertGptAttributes@@YAXPEAVVM_ROOT_EXTENSION@@EEPEAU_GUID@@1KPEAXPEAU_DEVICE_OBJECT@@@Z`
- size: `310`
- prototype: `void __fastcall(struct VM_ROOT_EXTENSION *, unsigned __int8, unsigned __int8, struct _GUID *, struct _GUID *, unsigned int, void *, struct _DEVICE_OBJECT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000f950`
- `0x140010d7c`

## callees

- `0x140005090`
- `0x140005240`
- `0x140010898`
- `0x140011d94`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140010988`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010988`

## pseudocode

```c
void __fastcall VmpCheckForRevertGptAttributes(
        struct VM_ROOT_EXTENSION *a1,
        char a2,
        __int64 a3,
        struct _GUID *a4,
        struct _GUID *a5,
        unsigned int a6,
        void *a7,
        struct _DEVICE_OBJECT *a8)
{
  unsigned int v8; // edi
  __int64 v9; // r10
  __int64 v10; // rbp
  unsigned int i; // esi
  __int64 v14; // rcx
  __int64 v15; // rcx
  bool v16; // zf
  unsigned __int64 v17; // rdx

  v8 = *((_DWORD *)a1 + 88);
  v9 = 0;
  v10 = *((_QWORD *)a1 + 45);
  for ( i = 0; i < v8; ++i )
  {
    v9 = v10 + 32LL * i;
    if ( a2 )
    {
      if ( *(_DWORD *)(v9 + 24) )
      {
        v14 = *(_QWORD *)&a4->Data1 - *(_QWORD *)v9;
        if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)v9 )
        {
          v15 = *(_QWORD *)a4->Data4;
          goto LABEL_6;
        }
        goto LABEL_7;
      }
    }
    else if ( (_BYTE)a3 )
    {
      if ( *(_DWORD *)(v9 + 28) )
      {
        v14 = *(_QWORD *)&a5->Data1 - *(_QWORD *)v9;
        if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)v9 )
        {
          v15 = *(_QWORD *)a5->Data4;
LABEL_6:
          v14 = v15 - *(_QWORD *)(v9 + 8);
        }
LABEL_7:
        v16 = v14 == 0;
        goto LABEL_15;
      }
    }
    else if ( !*(_DWORD *)(v9 + 24) && !*(_DWORD *)(v9 + 28) )
    {
      v16 = a6 == *(_DWORD *)v9;
LABEL_15:
      if ( v16 )
        break;
    }
  }
  if ( i != v8 )
  {
    v17 = *(_QWORD *)(v9 + 16);
    if ( a2 )
    {
      LOBYTE(a3) = 1;
      (*(void (__fastcall **)(void *, unsigned __int64, __int64))(*((_QWORD *)a1 + 49) + 176LL))(a7, v17, a3);
    }
    else
    {
      VmpDiskSetGptAttributes(a8, v17, a3);
    }
    --*((_DWORD *)a1 + 88);
    if ( i + 1 == v8 )
    {
      if ( !*((_DWORD *)a1 + 88) )
      {
        ExFreePoolWithTag(*((PVOID *)a1 + 45), 0);
        *((_QWORD *)a1 + 45) = 0;
      }
    }
    else
    {
      memmove((void *)(v10 + 32LL * i), (const void *)(v10 + 32LL * (i + 1)), 32LL * (v8 - i - 1));
    }
  }
}

```

## disassembly

```asm
0x140010898  push    rbx
0x14001089a  push    rbp
0x14001089b  push    rsi
0x14001089c  push    rdi
0x14001089d  push    r14
0x14001089f  sub     rsp, 20h
0x1400108a3  mov     edi, [rcx+160h]
0x1400108a9  xor     r10d, r10d
0x1400108ac  mov     rbp, [rcx+168h]
0x1400108b3  xor     esi, esi
0x1400108b5  mov     r14, r9
0x1400108b8  mov     r11b, dl
0x1400108bb  mov     rbx, rcx
0x1400108be  test    edi, edi
0x1400108c0  jz      short loc_14001092A
0x1400108c2  mov     r9d, [rsp+48h+arg_28]
0x1400108c7  mov     rdx, [rsp+48h+arg_20]
0x1400108cc  mov     r10d, esi
0x1400108cf  shl     r10, 5
0x1400108d3  add     r10, rbp
0x1400108d6  test    r11b, r11b
0x1400108d9  jz      short loc_1400108F7
0x1400108db  cmp     dword ptr [r10+18h], 0
0x1400108e0  jz      short loc_140010924
0x1400108e2  mov     rcx, [r14]
0x1400108e5  sub     rcx, [r10]
0x1400108e8  jnz     short loc_1400108F2
0x1400108ea  mov     rcx, [r14+8]
0x1400108ee  sub     rcx, [r10+8]
0x1400108f2  test    rcx, rcx
0x1400108f5  jmp     short loc_140010922
0x1400108f7  test    r8b, r8b
0x1400108fa  jz      short loc_140010911
0x1400108fc  cmp     dword ptr [r10+1Ch], 0
0x140010901  jz      short loc_140010924
0x140010903  mov     rcx, [rdx]
0x140010906  sub     rcx, [r10]
0x140010909  jnz     short loc_1400108F2
0x14001090b  mov     rcx, [rdx+8]
0x14001090f  jmp     short loc_1400108EE
0x140010911  cmp     dword ptr [r10+18h], 0
0x140010916  jnz     short loc_140010924
0x140010918  cmp     dword ptr [r10+1Ch], 0
0x14001091d  jnz     short loc_140010924
0x14001091f  cmp     r9d, [r10]
0x140010922  jz      short loc_14001092A
0x140010924  inc     esi
0x140010926  cmp     esi, edi
0x140010928  jb      short loc_1400108CC
0x14001092a  cmp     esi, edi
0x14001092c  jz      loc_1400109C2
0x140010932  mov     rdx, [r10+10h]; unsigned __int64
0x140010936  test    r11b, r11b
0x140010939  jz      short loc_14001095B
0x14001093b  mov     rax, [rbx+188h]
0x140010942  mov     r8b, 1
0x140010945  mov     rcx, [rsp+48h+arg_30]
0x14001094d  mov     rax, [rax+0B0h]
0x140010954  call    _guard_dispatch_icall
0x140010959  jmp     short loc_140010968
0x14001095b  mov     rcx, [rsp+48h+arg_38]; struct _DEVICE_OBJECT *
0x140010963  call    ?VmpDiskSetGptAttributes@@YAJPEAU_DEVICE_OBJECT@@_KE@Z; VmpDiskSetGptAttributes(_DEVICE_OBJECT *,unsigned __int64,uchar)
0x140010968  dec     dword ptr [rbx+160h]
0x14001096e  lea     eax, [rsi+1]
0x140010971  mov     ecx, [rbx+160h]
0x140010977  cmp     eax, edi
0x140010979  jnz     short loc_1400109A1
0x14001097b  test    ecx, ecx
0x14001097d  jnz     short loc_1400109C2
0x14001097f  mov     rcx, [rbx+168h]; P
0x140010986  xor     edx, edx; Tag
0x140010988  call    cs:__imp_ExFreePoolWithTag
0x14001098f  nop     dword ptr [rax+rax+00h]
0x140010994  mov     qword ptr [rbx+168h], 0
0x14001099f  jmp     short loc_1400109C2
0x1400109a1  sub     edi, esi
0x1400109a3  mov     edx, eax
0x1400109a5  shl     rdx, 5
0x1400109a9  mov     ecx, esi
0x1400109ab  add     rdx, rbp; Src
0x1400109ae  shl     rcx, 5
0x1400109b2  lea     r8d, [rdi-1]
0x1400109b6  add     rcx, rbp; void *
0x1400109b9  shl     r8, 5; Size
0x1400109bd  call    memmove
0x1400109c2  add     rsp, 20h
0x1400109c6  pop     r14
0x1400109c8  pop     rdi
0x1400109c9  pop     rsi
0x1400109ca  pop     rbp
0x1400109cb  pop     rbx
0x1400109cc  retn
```
