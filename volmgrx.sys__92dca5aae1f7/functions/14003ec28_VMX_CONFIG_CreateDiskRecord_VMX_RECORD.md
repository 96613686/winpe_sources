# VMX_CONFIG::CreateDiskRecord(VMX_RECORD * *)

- ea: `0x14003ec28`
- end: `0x14003eda8`
- name: `?CreateDiskRecord@VMX_CONFIG@@QEAAJPEAPEAVVMX_RECORD@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(VMX_CONFIG *__hidden this, struct VMX_RECORD **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14004a73c`

## callees

- `0x140005f80`
- `0x1400099d8`
- `0x14001b9a0`
- `0x14003ec28`
- `0x14003f05c`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x14003ecdc`
- `ntoskrnl!ExUuidCreate` at `0x14003ecdc`

## pseudocode

```c
__int64 __fastcall VMX_CONFIG::CreateDiskRecord(VMX_CONFIG *this, struct VMX_RECORD **a2)
{
  unsigned int v3; // ebx
  VMX_NOTIFICATION_QUEUE *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rbx
  struct VMX_RECORD *v7; // rdi
  NTSTATUS v8; // esi
  __int64 result; // rax
  struct VMX_RECORD *v10; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  v10 = 0;
  v3 = VMX_CONFIG::CreateRecord(this, &v10);
  if ( (v3 & 0x80000000) != 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v3;
    }
    v5 = 125;
LABEL_18:
    WPP_SF_d(*((_QWORD *)v4 + 3), v5, WPP_ecea8329fd353f2ede86956965576228_Traceguids, v3);
    return v3;
  }
  v6 = VMX_ALLOCATED_OBJECT::operator new(136, 256, 1767009622);
  if ( !v6 )
  {
    v4 = WPP_GLOBAL_Control;
    v3 = -1073741670;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v3;
    }
    v5 = 126;
    goto LABEL_18;
  }
  v7 = v10;
  *(_QWORD *)v6 = &VMX_DISK_INFO::`vftable';
  *(_QWORD *)(v6 + 48) = v7;
  *(_QWORD *)(v6 + 56) = 0;
  *(_BYTE *)(v6 + 64) = 1;
  v8 = ExUuidCreate((UUID *)(v6 + 72));
  if ( v8 >= 0 )
  {
    *(_DWORD *)(v6 + 96) |= 0x20u;
    *((_WORD *)v7 + 16) = 4;
    *((_QWORD *)v7 + 6) = v6;
    *((_WORD *)v7 + 32) |= 1u;
    result = 0;
    *a2 = v7;
  }
  else
  {
    (**(void (__fastcall ***)(__int64, __int64))v6)(v6, 1);
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        127,
        WPP_ecea8329fd353f2ede86956965576228_Traceguids,
        (unsigned int)v8);
    }
    return (unsigned int)v8;
  }
  return result;
}

```

## disassembly

```asm
0x14003ec28  mov     rax, rsp
0x14003ec2b  mov     [rax+8], rbx
0x14003ec2f  mov     [rax+18h], rsi
0x14003ec33  push    rdi
0x14003ec34  push    r14
0x14003ec36  push    r15
0x14003ec38  sub     rsp, 20h
0x14003ec3c  mov     r14, rdx
0x14003ec3f  mov     qword ptr [rdx], 0
0x14003ec46  lea     rdx, [rax+10h]; struct VMX_RECORD **
0x14003ec4a  mov     qword ptr [rax+10h], 0
0x14003ec52  call    ?CreateRecord@VMX_CONFIG@@QEAAJPEAPEAVVMX_RECORD@@@Z; VMX_CONFIG::CreateRecord(VMX_RECORD * *)
0x14003ec57  mov     ebx, eax
0x14003ec59  test    eax, eax
0x14003ec5b  jns     short loc_14003EC94
0x14003ec5d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ec64  lea     rdx, WPP_GLOBAL_Control
0x14003ec6b  cmp     rcx, rdx
0x14003ec6e  jz      loc_14003ED91
0x14003ec74  mov     edx, [rcx+2Ch]
0x14003ec77  test    dl, 20h
0x14003ec7a  jz      loc_14003ED91
0x14003ec80  cmp     byte ptr [rcx+29h], 2
0x14003ec84  jb      loc_14003ED91
0x14003ec8a  mov     edx, 7Dh ; '}'
0x14003ec8f  jmp     loc_14003ED7E
0x14003ec94  mov     edx, 100h; unsigned __int64
0x14003ec99  mov     r8d, 69526D56h; unsigned int
0x14003ec9f  lea     ecx, [rdx-78h]; unsigned __int64
0x14003eca2  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14003eca7  mov     rbx, rax
0x14003ecaa  test    rax, rax
0x14003ecad  jz      loc_14003ED54
0x14003ecb3  mov     rdi, [rsp+38h+arg_8]
0x14003ecb8  lea     rax, ??_7VMX_DISK_INFO@@6B@; const VMX_DISK_INFO::`vftable'
0x14003ecbf  mov     [rbx], rax
0x14003ecc2  lea     rcx, [rbx+48h]; Uuid
0x14003ecc6  mov     r15d, 1
0x14003eccc  mov     [rbx+30h], rdi
0x14003ecd0  mov     qword ptr [rbx+38h], 0
0x14003ecd8  mov     [rbx+40h], r15b
0x14003ecdc  call    cs:__imp_ExUuidCreate
0x14003ece3  nop     dword ptr [rax+rax+00h]
0x14003ece8  mov     esi, eax
0x14003ecea  test    eax, eax
0x14003ecec  jns     short loc_14003ED3A
0x14003ecee  mov     rcx, [rbx]
0x14003ecf1  mov     edx, r15d
0x14003ecf4  mov     rax, [rcx]
0x14003ecf7  mov     rcx, rbx
0x14003ecfa  call    _guard_dispatch_icall
0x14003ecff  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ed06  lea     rdx, WPP_GLOBAL_Control
0x14003ed0d  cmp     rcx, rdx
0x14003ed10  jz      short loc_14003ED36
0x14003ed12  mov     eax, [rcx+2Ch]
0x14003ed15  test    al, 20h
0x14003ed17  jz      short loc_14003ED36
0x14003ed19  cmp     byte ptr [rcx+29h], 2
0x14003ed1d  jb      short loc_14003ED36
0x14003ed1f  mov     rcx, [rcx+18h]
0x14003ed23  lea     edx, [r15+7Eh]
0x14003ed27  mov     r9d, esi
0x14003ed2a  lea     r8, WPP_ecea8329fd353f2ede86956965576228_Traceguids
0x14003ed31  call    WPP_SF_d
0x14003ed36  mov     eax, esi
0x14003ed38  jmp     short loc_14003ED93
0x14003ed3a  or      dword ptr [rbx+60h], 20h
0x14003ed3e  mov     word ptr [rdi+20h], 4
0x14003ed44  mov     [rdi+30h], rbx
0x14003ed48  or      [rdi+40h], r15w
0x14003ed4d  xor     eax, eax
0x14003ed4f  mov     [r14], rdi
0x14003ed52  jmp     short loc_14003ED93
0x14003ed54  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ed5b  lea     rdx, WPP_GLOBAL_Control
0x14003ed62  mov     ebx, 0C000009Ah
0x14003ed67  cmp     rcx, rdx
0x14003ed6a  jz      short loc_14003ED91
0x14003ed6c  mov     eax, [rcx+2Ch]
0x14003ed6f  test    al, 20h
0x14003ed71  jz      short loc_14003ED91
0x14003ed73  cmp     byte ptr [rcx+29h], 2
0x14003ed77  jb      short loc_14003ED91
0x14003ed79  mov     edx, 7Eh ; '~'
0x14003ed7e  mov     rcx, [rcx+18h]
0x14003ed82  lea     r8, WPP_ecea8329fd353f2ede86956965576228_Traceguids
0x14003ed89  mov     r9d, ebx
0x14003ed8c  call    WPP_SF_d
0x14003ed91  mov     eax, ebx
0x14003ed93  mov     rbx, [rsp+38h+arg_0]
0x14003ed98  mov     rsi, [rsp+38h+arg_10]
0x14003ed9d  add     rsp, 20h
0x14003eda1  pop     r15
0x14003eda3  pop     r14
0x14003eda5  pop     rdi
0x14003eda6  retn
```
