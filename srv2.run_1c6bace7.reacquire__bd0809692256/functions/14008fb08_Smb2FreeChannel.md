# Smb2FreeChannel

- ea: `0x14008fb08`
- end: `0x14008fbe6`
- name: `Smb2FreeChannel`
- size: `222`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140013990`

## callees

- `0x14000aab4`
- `0x14000ae60`
- `0x140013920`
- `0x14008fb08`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14008fb72`
- `ntoskrnl!ExDeleteResourceLite` at `0x14008fb72`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008fb83`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008fb83`
- `srvnet!SrvNetDecrementConnectionActiveCount` at `0x14008fb49`
- `srvnet!SrvNetDecrementConnectionActiveCount` at `0x14008fb49`
- `ksecdd!BCryptDestroyHash` at `0x14008fbb9`
- `ksecdd!BCryptDestroyHash` at `0x14008fbb9`

## pseudocode

```c
void __fastcall Smb2FreeChannel(char *P)
{
  void *v2; // rcx
  _QWORD *v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // rcx

  v2 = (void *)*((_QWORD *)P + 23);
  v3 = P + 64;
  if ( v2 )
  {
    if ( *(void **)(*v3 + 224LL) != v2 )
      BCryptDestroyHash(v2);
    *((_QWORD *)P + 23) = 0;
    *((_DWORD *)P + 49) = 0;
  }
  v4 = *((_QWORD *)P + 25);
  if ( v4 )
  {
    if ( *(_QWORD *)(*v3 + 240LL) != v4 )
      Smb2DeallocateSigningHashObject(v4);
    *((_DWORD *)P + 48) = 0;
    *((_QWORD *)P + 25) = 0;
  }
  v5 = *((_QWORD *)P + 7);
  if ( v5 )
  {
    SrvNetDecrementConnectionActiveCount(*(_QWORD *)(v5 + 480));
    Srv2DereferenceConnection(*((PVOID *)P + 7));
    *((_QWORD *)P + 7) = 0;
  }
  if ( *v3 )
  {
    Smb2DereferenceSession(*v3);
    *v3 = 0;
  }
  ExDeleteResourceLite((PERESOURCE)(P + 80));
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14008fb08  mov     [rsp+arg_0], rbx
0x14008fb0d  push    rdi
0x14008fb0e  sub     rsp, 20h
0x14008fb12  mov     rbx, rcx
0x14008fb15  mov     rcx, [rcx+0B8h]; hHash
0x14008fb1c  lea     rdi, [rbx+40h]
0x14008fb20  test    rcx, rcx
0x14008fb23  jnz     loc_14008FBA9
0x14008fb29  mov     rcx, [rbx+0C8h]
0x14008fb30  test    rcx, rcx
0x14008fb33  jnz     loc_14008FBCB
0x14008fb39  mov     rcx, [rbx+38h]
0x14008fb3d  test    rcx, rcx
0x14008fb40  jz      short loc_14008FB66
0x14008fb42  mov     rcx, [rcx+1E0h]
0x14008fb49  call    cs:__imp_SrvNetDecrementConnectionActiveCount
0x14008fb50  nop     dword ptr [rax+rax+00h]
0x14008fb55  mov     rcx, [rbx+38h]; P
0x14008fb59  call    Srv2DereferenceConnection
0x14008fb5e  mov     qword ptr [rbx+38h], 0
0x14008fb66  mov     rcx, [rdi]
0x14008fb69  test    rcx, rcx
0x14008fb6c  jnz     short loc_14008FB9B
0x14008fb6e  lea     rcx, [rbx+50h]; Resource
0x14008fb72  call    cs:__imp_ExDeleteResourceLite
0x14008fb79  nop     dword ptr [rax+rax+00h]
0x14008fb7e  xor     edx, edx; Tag
0x14008fb80  mov     rcx, rbx; P
0x14008fb83  call    cs:__imp_ExFreePoolWithTag
0x14008fb8a  nop     dword ptr [rax+rax+00h]
0x14008fb8f  mov     rbx, [rsp+28h+arg_0]
0x14008fb94  add     rsp, 20h
0x14008fb98  pop     rdi
0x14008fb99  retn
0x14008fb9b  call    Smb2DereferenceSession
0x14008fba0  mov     qword ptr [rdi], 0
0x14008fba7  jmp     short loc_14008FB6E
0x14008fba9  mov     rax, [rdi]
0x14008fbac  cmp     [rax+0E0h], rcx
0x14008fbb3  jz      loc_14009BBFA
0x14008fbb9  call    cs:__imp_BCryptDestroyHash
0x14008fbc0  nop     dword ptr [rax+rax+00h]
0x14008fbc5  nop
0x14008fbc6  jmp     loc_14009BBFA
0x14008fbcb  mov     rax, [rdi]
0x14008fbce  cmp     [rax+0F0h], rcx
0x14008fbd5  jz      loc_14009BC14
0x14008fbdb  call    Smb2DeallocateSigningHashObject
0x14008fbe0  nop
0x14008fbe1  jmp     loc_14009BC14
0x14009bbfa  mov     qword ptr [rbx+0B8h], 0
0x14009bc05  mov     dword ptr [rbx+0C4h], 0
0x14009bc0f  jmp     loc_14008FB29
0x14009bc14  mov     dword ptr [rbx+0C0h], 0
0x14009bc1e  mov     qword ptr [rbx+0C8h], 0
0x14009bc29  jmp     loc_14008FB39
```
