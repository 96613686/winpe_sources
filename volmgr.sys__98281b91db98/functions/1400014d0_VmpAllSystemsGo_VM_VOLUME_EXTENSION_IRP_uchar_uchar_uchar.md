# VmpAllSystemsGo(VM_VOLUME_EXTENSION *,_IRP *,uchar,uchar,uchar)

- ea: `0x1400014d0`
- end: `0x140001592`
- name: `?VmpAllSystemsGo@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@EEE@Z`
- size: `194`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *, unsigned __int8, unsigned __int8, char)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001ae0`
- `0x140004b40`
- `0x14000e010`
- `0x14000e150`
- `0x140016130`
- `0x140016540`
- `0x140016aa0`

## callees

- `0x1400014d0`
- `0x140002910`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000152e`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000157f`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000152e`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000157f`

## pseudocode

```c
__int64 __fastcall VmpAllSystemsGo(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2, char a3, char a4, char a5)
{
  __int64 result; // rax
  char v9; // cl

  if ( a2 )
    a2->IoStatus.Information = 0;
  result = VmpAcquireRundownShared(a1, a2);
  if ( (_DWORD)result != 259 )
  {
    if ( *((_BYTE *)a1 + 426) )
    {
      if ( *((_QWORD *)a1 + 54) )
        goto LABEL_6;
    }
    else if ( *((_QWORD *)a1 + 43) )
    {
LABEL_6:
      v9 = 1;
      goto LABEL_7;
    }
    v9 = 0;
LABEL_7:
    if ( a3 && !*((_BYTE *)a1 + 156) || a4 && !v9 )
    {
      ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)a1 + 14));
      return 3221225486LL;
    }
    else if ( a5 && *((_BYTE *)a1 + 160) )
    {
      ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)a1 + 14));
      return 2147483664LL;
    }
    else
    {
      return (unsigned int)result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400014d0  mov     [rsp+arg_0], rbx
0x1400014d5  mov     [rsp+arg_8], rsi
0x1400014da  push    rdi
0x1400014db  sub     rsp, 20h
0x1400014df  movzx   esi, r9b
0x1400014e3  movzx   edi, r8b
0x1400014e7  mov     rbx, rcx
0x1400014ea  test    rdx, rdx
0x1400014ed  jz      short loc_1400014F7
0x1400014ef  mov     qword ptr [rdx+38h], 0
0x1400014f7  call    ?VmpAcquireRundownShared@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpAcquireRundownShared(VM_VOLUME_EXTENSION *,_IRP *)
0x1400014fc  mov     edx, eax
0x1400014fe  cmp     eax, 103h
0x140001503  jz      short loc_14000153F
0x140001505  cmp     byte ptr [rbx+1AAh], 0
0x14000150c  jnz     short loc_14000156D
0x14000150e  cmp     qword ptr [rbx+158h], 0
0x140001516  jz      short loc_140001577
0x140001518  mov     cl, 1
0x14000151a  test    dil, dil
0x14000151d  jz      short loc_140001550
0x14000151f  movzx   eax, byte ptr [rbx+9Ch]
0x140001526  test    al, al
0x140001528  jnz     short loc_140001550
0x14000152a  mov     rcx, [rbx+70h]; RunRefCacheAware
0x14000152e  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140001535  nop     dword ptr [rax+rax+00h]
0x14000153a  mov     eax, 0C000000Eh
0x14000153f  mov     rbx, [rsp+28h+arg_0]
0x140001544  mov     rsi, [rsp+28h+arg_8]
0x140001549  add     rsp, 20h
0x14000154d  pop     rdi
0x14000154e  retn
0x140001550  test    sil, sil
0x140001553  jz      short loc_140001559
0x140001555  test    cl, cl
0x140001557  jz      short loc_14000152A
0x140001559  cmp     [rsp+28h+arg_20], 0
0x14000155e  jz      short loc_140001569
0x140001560  cmp     byte ptr [rbx+0A0h], 0
0x140001567  jnz     short loc_14000157B
0x140001569  mov     eax, edx
0x14000156b  jmp     short loc_14000153F
0x14000156d  cmp     qword ptr [rbx+1B0h], 0
0x140001575  jnz     short loc_140001518
0x140001577  xor     cl, cl
0x140001579  jmp     short loc_14000151A
0x14000157b  mov     rcx, [rbx+70h]; RunRefCacheAware
0x14000157f  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140001586  nop     dword ptr [rax+rax+00h]
0x14000158b  mov     eax, 80000010h
0x140001590  jmp     short loc_14000153F
```
