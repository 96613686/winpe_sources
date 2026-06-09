# WofPreQueryOpenCallback

- ea: `0x14003b910`
- end: `0x14003b9b0`
- name: `WofPreQueryOpenCallback`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400014d0`
- `0x14003b910`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x14003b969`
- `FLTMGR!FltReleaseContext` at `0x14003b969`

## pseudocode

```c
__int64 __fastcall WofPreQueryOpenCallback(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rax
  __int64 v6; // r9
  int VolumeContext; // eax
  PFLT_CONTEXT v8; // rdx
  unsigned int v9; // ebx
  int v11; // ecx
  PFLT_CONTEXT Context; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(a1 + 16);
  Context = 0;
  v6 = *(_QWORD *)(v3 + 8);
  if ( *(_QWORD *)(v6 + 96) && *(_WORD *)(v6 + 88) || *(_QWORD *)(v6 + 64) )
  {
    VolumeContext = WofGetVolumeContext(*(PFLT_INSTANCE *)(a2 + 24), &Context);
    v8 = Context;
    v9 = 1;
    if ( VolumeContext >= 0 && (*((_DWORD *)Context + 14) & 1) == 0 )
    {
      *a3 = 0;
      v11 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 48LL);
      if ( v11 == 68 || v11 == 70 || (v9 = 6, v11 == 77) )
        v9 = 0;
    }
    if ( v8 )
      FltReleaseContext(v8);
  }
  else
  {
    return 1;
  }
  return v9;
}

```

## disassembly

```asm
0x14003b910  push    rbx
0x14003b912  push    rbp
0x14003b913  push    rsi
0x14003b914  push    rdi
0x14003b915  sub     rsp, 28h
0x14003b919  mov     rax, [rcx+10h]
0x14003b91d  xor     ebp, ebp
0x14003b91f  mov     rsi, r8
0x14003b922  mov     [rsp+48h+Context], rbp
0x14003b927  mov     r8, rdx
0x14003b92a  mov     rdi, rcx
0x14003b92d  mov     r9, [rax+8]
0x14003b931  cmp     [r9+60h], rbp
0x14003b935  jz      short loc_14003B981
0x14003b937  cmp     [r9+58h], bp
0x14003b93c  jz      short loc_14003B981
0x14003b93e  mov     rcx, [r8+18h]; Instance
0x14003b942  lea     rdx, [rsp+48h+Context]
0x14003b947  call    WofGetVolumeContext
0x14003b94c  mov     rdx, [rsp+48h+Context]
0x14003b951  mov     ebx, 1
0x14003b956  test    eax, eax
0x14003b958  js      short loc_14003B961
0x14003b95a  mov     eax, [rdx+38h]
0x14003b95d  test    bl, al
0x14003b95f  jz      short loc_14003B98E
0x14003b961  test    rdx, rdx
0x14003b964  jz      short loc_14003B975
0x14003b966  mov     rcx, rdx; Context
0x14003b969  call    cs:__imp_FltReleaseContext
0x14003b970  nop     dword ptr [rax+rax+00h]
0x14003b975  mov     eax, ebx
0x14003b977  add     rsp, 28h
0x14003b97b  pop     rdi
0x14003b97c  pop     rsi
0x14003b97d  pop     rbp
0x14003b97e  pop     rbx
0x14003b97f  retn
0x14003b981  cmp     [r9+40h], rbp
0x14003b985  jnz     short loc_14003B93E
0x14003b987  mov     ebx, 1
0x14003b98c  jmp     short loc_14003B975
0x14003b98e  mov     [rsi], rbp
0x14003b991  mov     rax, [rdi+10h]
0x14003b995  mov     ecx, [rax+30h]
0x14003b998  cmp     ecx, 44h ; 'D'
0x14003b99b  jz      short loc_14003B9AC
0x14003b99d  cmp     ecx, 46h ; 'F'
0x14003b9a0  jz      short loc_14003B9AC
0x14003b9a2  mov     ebx, 6
0x14003b9a7  cmp     ecx, 4Dh ; 'M'
0x14003b9aa  jnz     short loc_14003B961
0x14003b9ac  mov     ebx, ebp
0x14003b9ae  jmp     short loc_14003B961
```
