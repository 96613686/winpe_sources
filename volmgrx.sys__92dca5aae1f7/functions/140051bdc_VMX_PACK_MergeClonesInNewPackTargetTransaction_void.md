# VMX_PACK::MergeClonesInNewPackTargetTransaction(void)

- ea: `0x140051bdc`
- end: `0x140051dac`
- name: `?MergeClonesInNewPackTargetTransaction@VMX_PACK@@QEAAJXZ`
- size: `464`
- prototype: `__int64 __fastcall(VMX_PACK *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14002b13c`

## callees

- `0x1400097c0`
- `0x1400099d8`
- `0x14002aed4`
- `0x14004037c`
- `0x140040580`
- `0x140041adc`
- `0x140041bb8`
- `0x140050afc`
- `0x140050bf0`
- `0x1400516b0`
- `0x140051bdc`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x140051c3f`
- `ntoskrnl!ExUuidCreate` at `0x140051c3f`

## pseudocode

```c
__int64 __fastcall VMX_PACK::MergeClonesInNewPackTargetTransaction(VMX_PACK *this)
{
  __int64 v1; // rsi
  signed __int16 *i; // rdi
  signed __int16 *v4; // rax
  NTSTATUS v5; // ebx
  __int64 v6; // r14
  unsigned __int64 GptAttributes; // rax
  VMX_RECORD *j; // rdi
  __int64 v9; // rcx
  __int16 v10; // ax
  __int64 v11; // rbx
  __int128 v12; // xmm0
  VMX_RECORD *v13; // rdi
  __int64 v14; // rcx

  v1 = *((_QWORD *)this + 6);
  VMX_PACK::MarkSelfContained(this, (struct VMX_CHANGE_IDENTITY_TRANSACTION *)v1);
  for ( i = *(signed __int16 **)(*((_QWORD *)this + 2) + 16LL); ; i = *(signed __int16 **)i )
  {
    v4 = (signed __int16 *)(*((_QWORD *)this + 2) + 16LL);
    if ( i == v4 )
      break;
    if ( i[16] == 1 )
    {
      if ( _bittest16(i + 32, 0xAu) )
      {
        v5 = VMX_RECORD::PreTouch((VMX_RECORD *)i);
        if ( v5 < 0 )
          goto LABEL_22;
        v6 = *((_QWORD *)i + 6);
        v5 = ExUuidCreate((UUID *)(v6 + 232));
        if ( v5 < 0 )
          goto LABEL_22;
        GptAttributes = VMX_VOLUME_INFO::QueryGptAttributes((VMX_VOLUME_INFO *)v6);
        VMX_VOLUME_INFO::SetGptAttributes((VMX_VOLUME_INFO *)v6, GptAttributes | 0xF000000000000000uLL);
        VMX_VOLUME_INFO::SetDriveLetter((VMX_VOLUME_INFO *)v6, 0);
        VMX_RECORD::Touch((VMX_RECORD *)i, *((struct VMX_TRANSACTION **)this + 6));
      }
      else
      {
        v5 = VMX_PACK::DeleteVolumeTransaction(this, (struct VMX_RECORD *)i);
        if ( v5 < 0 )
          goto LABEL_22;
      }
      i[32] &= ~0x10u;
    }
  }
  for ( j = *(VMX_RECORD **)v4; ; j = *(VMX_RECORD **)j )
  {
    v9 = *((_QWORD *)this + 2);
    if ( j == (VMX_RECORD *)(v9 + 16) )
      break;
    if ( *((_WORD *)j + 16) == 4 )
    {
      v5 = VMX_RECORD::PreTouch(j);
      if ( v5 < 0 )
        goto LABEL_22;
      v10 = *((_WORD *)j + 32);
      if ( (v10 & 0x200) != 0 )
      {
        v11 = *((_QWORD *)j + 6);
        v12 = *((_OWORD *)VMX_CHANGE_IDENTITY_TRANSACTION::FindDiskByOldDiskId(
                            (VMX_CHANGE_IDENTITY_TRANSACTION *)v1,
                            (struct _GUID *)(v11 + 72))
              + 1);
        *(_DWORD *)(v11 + 96) &= ~0x20u;
        *(_OWORD *)(v11 + 72) = v12;
      }
      else
      {
        *((_WORD *)j + 32) = v10 | 8;
        --*(_DWORD *)(v1 + 20);
      }
      VMX_RECORD::Touch(j, (struct VMX_TRANSACTION *)v1);
    }
  }
  v13 = *(VMX_RECORD **)(v9 + 32);
  v5 = VMX_RECORD::PreTouch(v13);
  if ( v5 >= 0 )
  {
    v14 = *((_QWORD *)v13 + 6);
    *(_OWORD *)(v14 + 72) = *(_OWORD *)(v1 + 112);
    RtlStringCbCopyA((NTSTRSAFE_PSTR)(v14 + 16), 0x20u, (NTSTRSAFE_PCSTR)(v1 + 128));
    VMX_RECORD::Touch(v13, (struct VMX_TRANSACTION *)v1);
    *(_BYTE *)(v1 + 177) = 1;
    return (unsigned int)v5;
  }
LABEL_22:
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      186,
      WPP_b525482092043ba595507d12d78e6f73_Traceguids,
      (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140051bdc  push    rbx
0x140051bde  push    rbp
0x140051bdf  push    rsi
0x140051be0  push    rdi
0x140051be1  push    r14
0x140051be3  sub     rsp, 20h
0x140051be7  mov     rsi, [rcx+30h]
0x140051beb  mov     rbp, rcx
0x140051bee  mov     rdx, rsi; struct VMX_CHANGE_IDENTITY_TRANSACTION *
0x140051bf1  call    ?MarkSelfContained@VMX_PACK@@QEAAXPEAVVMX_CHANGE_IDENTITY_TRANSACTION@@@Z; VMX_PACK::MarkSelfContained(VMX_CHANGE_IDENTITY_TRANSACTION *)
0x140051bf6  mov     rax, [rbp+10h]
0x140051bfa  mov     rdi, [rax+10h]
0x140051bfe  mov     rax, [rbp+10h]
0x140051c02  add     rax, 10h
0x140051c06  cmp     rdi, rax
0x140051c09  jz      loc_140051CB0
0x140051c0f  cmp     word ptr [rdi+20h], 1
0x140051c14  jnz     loc_140051CA8
0x140051c1a  bt      word ptr [rdi+40h], 0Ah
0x140051c20  jnb     short loc_140051C8A
0x140051c22  mov     rcx, rdi; this
0x140051c25  call    ?PreTouch@VMX_RECORD@@QEAAJXZ; VMX_RECORD::PreTouch(void)
0x140051c2a  mov     ebx, eax
0x140051c2c  test    eax, eax
0x140051c2e  js      loc_140051D66
0x140051c34  mov     r14, [rdi+30h]
0x140051c38  lea     rcx, [r14+0E8h]; Uuid
0x140051c3f  call    cs:__imp_ExUuidCreate
0x140051c46  nop     dword ptr [rax+rax+00h]
0x140051c4b  mov     ebx, eax
0x140051c4d  test    eax, eax
0x140051c4f  js      loc_140051D66
0x140051c55  mov     rcx, r14; this
0x140051c58  call    ?QueryGptAttributes@VMX_VOLUME_INFO@@QEAA_KXZ; VMX_VOLUME_INFO::QueryGptAttributes(void)
0x140051c5d  mov     rdx, 0F000000000000000h
0x140051c67  mov     rcx, r14; this
0x140051c6a  or      rdx, rax; unsigned __int64
0x140051c6d  call    ?SetGptAttributes@VMX_VOLUME_INFO@@QEAAX_K@Z; VMX_VOLUME_INFO::SetGptAttributes(unsigned __int64)
0x140051c72  xor     edx, edx; unsigned __int8
0x140051c74  mov     rcx, r14; this
0x140051c77  call    ?SetDriveLetter@VMX_VOLUME_INFO@@QEAAJE@Z; VMX_VOLUME_INFO::SetDriveLetter(uchar)
0x140051c7c  mov     rdx, [rbp+30h]; struct VMX_TRANSACTION *
0x140051c80  mov     rcx, rdi; this
0x140051c83  call    ?Touch@VMX_RECORD@@QEAAXPEAVVMX_TRANSACTION@@@Z; VMX_RECORD::Touch(VMX_TRANSACTION *)
0x140051c88  jmp     short loc_140051C9F
0x140051c8a  mov     rdx, rdi; struct VMX_RECORD *
0x140051c8d  mov     rcx, rbp; this
0x140051c90  call    ?DeleteVolumeTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::DeleteVolumeTransaction(VMX_RECORD *)
0x140051c95  mov     ebx, eax
0x140051c97  test    eax, eax
0x140051c99  js      loc_140051D66
0x140051c9f  mov     eax, 0FFEFh
0x140051ca4  and     [rdi+40h], ax
0x140051ca8  mov     rdi, [rdi]
0x140051cab  jmp     loc_140051BFE
0x140051cb0  mov     rdi, [rax]
0x140051cb3  mov     rcx, [rbp+10h]
0x140051cb7  lea     rax, [rcx+10h]
0x140051cbb  cmp     rdi, rax
0x140051cbe  jz      short loc_140051D1E
0x140051cc0  cmp     word ptr [rdi+20h], 4
0x140051cc5  jnz     short loc_140051D19
0x140051cc7  mov     rcx, rdi; this
0x140051cca  call    ?PreTouch@VMX_RECORD@@QEAAJXZ; VMX_RECORD::PreTouch(void)
0x140051ccf  mov     ebx, eax
0x140051cd1  test    eax, eax
0x140051cd3  js      loc_140051D66
0x140051cd9  movzx   eax, word ptr [rdi+40h]
0x140051cdd  bt      ax, 9
0x140051ce2  jnb     short loc_140051D03
0x140051ce4  mov     rbx, [rdi+30h]
0x140051ce8  mov     rcx, rsi; this
0x140051ceb  lea     rdx, [rbx+48h]; struct _GUID *
0x140051cef  call    ?FindDiskByOldDiskId@VMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAVVMX_DISK_TRANSLATION@@PEAU_GUID@@@Z; VMX_CHANGE_IDENTITY_TRANSACTION::FindDiskByOldDiskId(_GUID *)
0x140051cf4  movups  xmm0, xmmword ptr [rax+10h]
0x140051cf8  and     dword ptr [rbx+60h], 0FFFFFFDFh
0x140051cfc  movdqu  xmmword ptr [rbx+48h], xmm0
0x140051d01  jmp     short loc_140051D0E
0x140051d03  or      ax, 8
0x140051d07  mov     [rdi+40h], ax
0x140051d0b  dec     dword ptr [rsi+14h]
0x140051d0e  mov     rdx, rsi; struct VMX_TRANSACTION *
0x140051d11  mov     rcx, rdi; this
0x140051d14  call    ?Touch@VMX_RECORD@@QEAAXPEAVVMX_TRANSACTION@@@Z; VMX_RECORD::Touch(VMX_TRANSACTION *)
0x140051d19  mov     rdi, [rdi]
0x140051d1c  jmp     short loc_140051CB3
0x140051d1e  mov     rdi, [rcx+20h]
0x140051d22  mov     rcx, rdi; this
0x140051d25  call    ?PreTouch@VMX_RECORD@@QEAAJXZ; VMX_RECORD::PreTouch(void)
0x140051d2a  mov     ebx, eax
0x140051d2c  test    eax, eax
0x140051d2e  js      short loc_140051D66
0x140051d30  mov     rcx, [rdi+30h]
0x140051d34  lea     r8, [rsi+80h]; pszSrc
0x140051d3b  movups  xmm0, xmmword ptr [rsi+70h]
0x140051d3f  mov     edx, 20h ; ' '; cbDest
0x140051d44  movdqu  xmmword ptr [rcx+48h], xmm0
0x140051d49  add     rcx, 10h; pszDest
0x140051d4d  call    RtlStringCbCopyA
0x140051d52  mov     rdx, rsi; struct VMX_TRANSACTION *
0x140051d55  mov     rcx, rdi; this
0x140051d58  call    ?Touch@VMX_RECORD@@QEAAXPEAVVMX_TRANSACTION@@@Z; VMX_RECORD::Touch(VMX_TRANSACTION *)
0x140051d5d  mov     byte ptr [rsi+0B1h], 1
0x140051d64  jmp     short loc_140051D9E
0x140051d66  mov     rcx, cs:WPP_GLOBAL_Control
0x140051d6d  lea     rax, WPP_GLOBAL_Control
0x140051d74  cmp     rcx, rax
0x140051d77  jz      short loc_140051D9E
0x140051d79  mov     eax, [rcx+2Ch]
0x140051d7c  test    al, 8
0x140051d7e  jz      short loc_140051D9E
0x140051d80  cmp     byte ptr [rcx+29h], 2
0x140051d84  jb      short loc_140051D9E
0x140051d86  mov     rcx, [rcx+18h]
0x140051d8a  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x140051d91  mov     edx, 0BAh
0x140051d96  mov     r9d, ebx
0x140051d99  call    WPP_SF_d
0x140051d9e  mov     eax, ebx
0x140051da0  add     rsp, 20h
0x140051da4  pop     r14
0x140051da6  pop     rdi
0x140051da7  pop     rsi
0x140051da8  pop     rbp
0x140051da9  pop     rbx
0x140051daa  retn
```
