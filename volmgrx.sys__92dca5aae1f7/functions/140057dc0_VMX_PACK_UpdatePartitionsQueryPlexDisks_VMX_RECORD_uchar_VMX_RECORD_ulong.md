# VMX_PACK::UpdatePartitionsQueryPlexDisks(VMX_RECORD *,uchar,VMX_RECORD * * *,ulong *)

- ea: `0x140057dc0`
- end: `0x140057f4e`
- name: `?UpdatePartitionsQueryPlexDisks@VMX_PACK@@QEAAJPEAVVMX_RECORD@@EPEAPEAPEAV2@PEAK@Z`
- size: `398`
- prototype: `__int64 __fastcall(VMX_PACK *this, struct VMX_RECORD *, char, struct VMX_RECORD ***, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1400302dc`
- `0x140035e3c`

## callees

- `0x1400099d8`
- `0x140009fcc`
- `0x140057dc0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140057e13`
- `ntoskrnl!ExAllocatePool2` at `0x140057e13`

## pseudocode

```c
__int64 __fastcall VMX_PACK::UpdatePartitionsQueryPlexDisks(
        VMX_PACK *this,
        struct VMX_RECORD *a2,
        char a3,
        struct VMX_RECORD ***a4,
        unsigned int *a5)
{
  __int64 v6; // rax
  __int64 v8; // rdi
  struct VMX_RECORD **Pool2; // rdx
  VMX_NOTIFICATION_QUEUE *v10; // rcx
  __int64 v11; // rdx
  VMX_NOTIFICATION_QUEUE *v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rax

  v6 = *((_WORD *)a2 + 32) & 1;
  *a4 = 0;
  *a5 = 0;
  v8 = *((_QWORD *)a2 + v6 + 5);
  if ( *(_BYTE *)(v8 + 87) == 2 && *(_DWORD *)(v8 + 92) == 1 )
  {
    Pool2 = (struct VMX_RECORD **)ExAllocatePool2(258, 8, 538996054);
    if ( Pool2 )
    {
      v15 = *(_QWORD *)(*(_QWORD *)(v8 + 152) + 8LL * (*(_WORD *)(*(_QWORD *)(v8 + 152) + 64LL) & 1) + 40);
      *a4 = Pool2;
      *a5 = 1;
      *Pool2 = *(struct VMX_RECORD **)(v15 + 152);
      return 0;
    }
    if ( a3 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
      {
        return 0;
      }
      v11 = 107;
      goto LABEL_19;
    }
    v12 = WPP_GLOBAL_Control;
    v13 = -1073741670;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v14 = 108;
LABEL_25:
      WPP_SF_d(*((_QWORD *)v12 + 3), v14, WPP_b525482092043ba595507d12d78e6f73_Traceguids, v13);
    }
  }
  else
  {
    if ( a3 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
      {
        return 0;
      }
      v11 = 105;
LABEL_19:
      WPP_SF_(*((_QWORD *)v10 + 3), v11, WPP_b525482092043ba595507d12d78e6f73_Traceguids);
      return 0;
    }
    v12 = WPP_GLOBAL_Control;
    v13 = -1070071744;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v14 = 106;
      goto LABEL_25;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x140057dc0  push    rbx
0x140057dc2  push    rsi
0x140057dc3  push    rdi
0x140057dc4  push    r14
0x140057dc6  sub     rsp, 28h
0x140057dca  movzx   eax, word ptr [rdx+40h]
0x140057dce  mov     rsi, r9
0x140057dd1  mov     r14, [rsp+48h+arg_20]
0x140057dd6  and     eax, 1
0x140057dd9  mov     qword ptr [r9], 0
0x140057de0  mov     bl, r8b
0x140057de3  mov     dword ptr [r14], 0
0x140057dea  mov     rdi, [rdx+rax*8+28h]
0x140057def  cmp     byte ptr [rdi+57h], 2
0x140057df3  jnz     loc_140057EC6
0x140057df9  cmp     dword ptr [rdi+5Ch], 1
0x140057dfd  jnz     loc_140057EC6
0x140057e03  mov     edx, 8
0x140057e08  mov     ecx, 102h
0x140057e0d  mov     r8d, 20206D56h
0x140057e13  call    cs:__imp_ExAllocatePool2
0x140057e1a  nop     dword ptr [rax+rax+00h]
0x140057e1f  mov     rdx, rax
0x140057e22  test    rax, rax
0x140057e25  jnz     short loc_140057E9D
0x140057e27  test    bl, bl
0x140057e29  jz      short loc_140057E61
0x140057e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140057e32  lea     rax, WPP_GLOBAL_Control
0x140057e39  cmp     rcx, rax
0x140057e3c  jz      loc_140057EFF
0x140057e42  mov     eax, [rcx+2Ch]
0x140057e45  test    al, 8
0x140057e47  jz      loc_140057EFF
0x140057e4d  cmp     byte ptr [rcx+29h], 3
0x140057e51  jb      loc_140057EFF
0x140057e57  mov     edx, 6Bh ; 'k'
0x140057e5c  jmp     loc_140057EEF
0x140057e61  mov     rcx, cs:WPP_GLOBAL_Control
0x140057e68  lea     rax, WPP_GLOBAL_Control
0x140057e6f  mov     ebx, 0C000009Ah
0x140057e74  cmp     rcx, rax
0x140057e77  jz      loc_140057F41
0x140057e7d  mov     edx, [rcx+2Ch]
0x140057e80  test    dl, 8
0x140057e83  jz      loc_140057F41
0x140057e89  cmp     byte ptr [rcx+29h], 2
0x140057e8d  jb      loc_140057F41
0x140057e93  mov     edx, 6Ch ; 'l'
0x140057e98  jmp     loc_140057F2E
0x140057e9d  mov     rcx, [rdi+98h]
0x140057ea4  movzx   eax, word ptr [rcx+40h]
0x140057ea8  and     eax, 1
0x140057eab  mov     rax, [rcx+rax*8+28h]
0x140057eb0  mov     [rsi], rdx
0x140057eb3  mov     dword ptr [r14], 1
0x140057eba  mov     rcx, [rax+98h]
0x140057ec1  mov     [rdx], rcx
0x140057ec4  jmp     short loc_140057EFF
0x140057ec6  test    bl, bl
0x140057ec8  jz      short loc_140057F03
0x140057eca  mov     rcx, cs:WPP_GLOBAL_Control
0x140057ed1  lea     rax, WPP_GLOBAL_Control
0x140057ed8  cmp     rcx, rax
0x140057edb  jz      short loc_140057EFF
0x140057edd  mov     eax, [rcx+2Ch]
0x140057ee0  test    al, 8
0x140057ee2  jz      short loc_140057EFF
0x140057ee4  cmp     byte ptr [rcx+29h], 3
0x140057ee8  jb      short loc_140057EFF
0x140057eea  mov     edx, 69h ; 'i'
0x140057eef  mov     rcx, [rcx+18h]
0x140057ef3  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x140057efa  call    WPP_SF_
0x140057eff  xor     eax, eax
0x140057f01  jmp     short loc_140057F43
0x140057f03  mov     rcx, cs:WPP_GLOBAL_Control
0x140057f0a  lea     rax, WPP_GLOBAL_Control
0x140057f11  mov     ebx, 0C0380040h
0x140057f16  cmp     rcx, rax
0x140057f19  jz      short loc_140057F41
0x140057f1b  mov     edx, [rcx+2Ch]
0x140057f1e  test    dl, 8
0x140057f21  jz      short loc_140057F41
0x140057f23  cmp     byte ptr [rcx+29h], 2
0x140057f27  jb      short loc_140057F41
0x140057f29  mov     edx, 6Ah ; 'j'
0x140057f2e  mov     rcx, [rcx+18h]
0x140057f32  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x140057f39  mov     r9d, ebx
0x140057f3c  call    WPP_SF_d
0x140057f41  mov     eax, ebx
0x140057f43  add     rsp, 28h
0x140057f47  pop     r14
0x140057f49  pop     rdi
0x140057f4a  pop     rsi
0x140057f4b  pop     rbx
0x140057f4c  retn
```
