# WofPreQueryOpenCallback

- ea: `0x14003b8c0`
- end: `0x14003b960`
- name: `WofPreQueryOpenCallback`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400014d0`
- `0x14003b8c0`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x14003b919`
- `FLTMGR!FltReleaseContext` at `0x14003b919`

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
0x14003b8c0  push    rbx
0x14003b8c2  push    rbp
0x14003b8c3  push    rsi
0x14003b8c4  push    rdi
0x14003b8c5  sub     rsp, 28h
0x14003b8c9  mov     rax, [rcx+10h]
0x14003b8cd  xor     ebp, ebp
0x14003b8cf  mov     rsi, r8
0x14003b8d2  mov     [rsp+48h+Context], rbp
0x14003b8d7  mov     r8, rdx
0x14003b8da  mov     rdi, rcx
0x14003b8dd  mov     r9, [rax+8]
0x14003b8e1  cmp     [r9+60h], rbp
0x14003b8e5  jz      short loc_14003B931
0x14003b8e7  cmp     [r9+58h], bp
0x14003b8ec  jz      short loc_14003B931
0x14003b8ee  mov     rcx, [r8+18h]; Instance
0x14003b8f2  lea     rdx, [rsp+48h+Context]
0x14003b8f7  call    WofGetVolumeContext
0x14003b8fc  mov     rdx, [rsp+48h+Context]
0x14003b901  mov     ebx, 1
0x14003b906  test    eax, eax
0x14003b908  js      short loc_14003B911
0x14003b90a  mov     eax, [rdx+38h]
0x14003b90d  test    bl, al
0x14003b90f  jz      short loc_14003B93E
0x14003b911  test    rdx, rdx
0x14003b914  jz      short loc_14003B925
0x14003b916  mov     rcx, rdx; Context
0x14003b919  call    cs:__imp_FltReleaseContext
0x14003b920  nop     dword ptr [rax+rax+00h]
0x14003b925  mov     eax, ebx
0x14003b927  add     rsp, 28h
0x14003b92b  pop     rdi
0x14003b92c  pop     rsi
0x14003b92d  pop     rbp
0x14003b92e  pop     rbx
0x14003b92f  retn
0x14003b931  cmp     [r9+40h], rbp
0x14003b935  jnz     short loc_14003B8EE
0x14003b937  mov     ebx, 1
0x14003b93c  jmp     short loc_14003B925
0x14003b93e  mov     [rsi], rbp
0x14003b941  mov     rax, [rdi+10h]
0x14003b945  mov     ecx, [rax+30h]
0x14003b948  cmp     ecx, 44h ; 'D'
0x14003b94b  jz      short loc_14003B95C
0x14003b94d  cmp     ecx, 46h ; 'F'
0x14003b950  jz      short loc_14003B95C
0x14003b952  mov     ebx, 6
0x14003b957  cmp     ecx, 4Dh ; 'M'
0x14003b95a  jnz     short loc_14003B911
0x14003b95c  mov     ebx, ebp
0x14003b95e  jmp     short loc_14003B911
```
