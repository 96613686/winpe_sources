# VMX_CONFIG::CreateVolumeRecord(_GUID *,VMX_RECORD * *)

- ea: `0x14003f258`
- end: `0x14003f46c`
- name: `?CreateVolumeRecord@VMX_CONFIG@@QEAAJPEAU_GUID@@PEAPEAVVMX_RECORD@@@Z`
- size: `532`
- prototype: `__int64 __fastcall(VMX_CONFIG *__hidden this, struct _GUID *, struct VMX_RECORD **)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14004a88c`
- `0x14005013c`
- `0x140055a78`

## callees

- `0x140005f80`
- `0x1400097c0`
- `0x1400099d8`
- `0x14001b9a0`
- `0x14003f05c`
- `0x14003f258`
- `0x140040270`
- `0x140041bb8`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x14003f3bc`
- `ntoskrnl!ExUuidCreate` at `0x14003f3bc`

## pseudocode

```c
__int64 __fastcall VMX_CONFIG::CreateVolumeRecord(VMX_CONFIG *this, struct _GUID *a2, struct VMX_RECORD **a3)
{
  unsigned int v6; // ebx
  VMX_NOTIFICATION_QUEUE *v7; // r10
  __int64 v8; // rdx
  __int64 v9; // rbx
  struct VMX_RECORD *v10; // rdi
  __int64 v11; // rax
  __int64 result; // rax
  NTSTATUS v13; // esi
  struct VMX_RECORD *v14; // [rsp+70h] [rbp+18h] BYREF

  v14 = 0;
  *a3 = 0;
  v6 = VMX_CONFIG::CreateRecord(this, &v14);
  if ( (v6 & 0x80000000) != 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v6;
    }
    v8 = 118;
LABEL_23:
    WPP_SF_d(*((_QWORD *)v7 + 3), v8, WPP_ecea8329fd353f2ede86956965576228_Traceguids, v6);
    return v6;
  }
  v9 = VMX_ALLOCATED_OBJECT::operator new(272, 256, 1767009622);
  if ( !v9 )
  {
    v7 = WPP_GLOBAL_Control;
    v6 = -1073741670;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v6;
    }
    v8 = 119;
    goto LABEL_23;
  }
  v10 = v14;
  *(_QWORD *)v9 = &VMX_VOLUME_INFO::`vftable';
  *(_QWORD *)(v9 + 48) = v10;
  *(_QWORD *)(v9 + 56) = 0;
  *(_BYTE *)(v9 + 64) = 1;
  RtlStringCbCopyA((NTSTRSAFE_PSTR)(v9 + 72), 0x20u, "gen");
  *(_BYTE *)(v9 + 136) = 3;
  RtlStringCbCopyA((NTSTRSAFE_PSTR)(v9 + 121), 0xFu, "ACTIVE");
  VMX_CONFIG::NextVolumeMinor(this, (unsigned int *)(v9 + 152));
  *(_DWORD *)(v9 + 156) = 17;
  *(_DWORD *)(v9 + 200) = 6;
  VMX_VOLUME_INFO::SetGptAttributes((VMX_VOLUME_INFO *)v9, 0x8000000000000000uLL);
  if ( a2 )
  {
    v11 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v11 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( v11 )
    {
      *(struct _GUID *)(v9 + 232) = *a2;
LABEL_12:
      *((_WORD *)v10 + 16) = 1;
      *((_QWORD *)v10 + 6) = v9;
      *((_WORD *)v10 + 32) |= 1u;
      result = 0;
      *a3 = v10;
      return result;
    }
  }
  v13 = ExUuidCreate((UUID *)(v9 + 232));
  if ( v13 >= 0 )
    goto LABEL_12;
  (**(void (__fastcall ***)(__int64, __int64))v9)(v9, 1);
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      120,
      WPP_ecea8329fd353f2ede86956965576228_Traceguids,
      (unsigned int)v13);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14003f258  push    rbx
0x14003f25a  push    rbp
0x14003f25b  push    rsi
0x14003f25c  push    rdi
0x14003f25d  push    r12
0x14003f25f  push    r14
0x14003f261  sub     rsp, 28h
0x14003f265  mov     rsi, rdx
0x14003f268  mov     [rsp+58h+arg_10], 0
0x14003f271  lea     rdx, [rsp+58h+arg_10]; struct VMX_RECORD **
0x14003f276  mov     qword ptr [r8], 0
0x14003f27d  mov     r14, r8
0x14003f280  mov     rbp, rcx
0x14003f283  call    ?CreateRecord@VMX_CONFIG@@QEAAJPEAPEAVVMX_RECORD@@@Z; VMX_CONFIG::CreateRecord(VMX_RECORD * *)
0x14003f288  mov     ebx, eax
0x14003f28a  test    eax, eax
0x14003f28c  jns     short loc_14003F2C7
0x14003f28e  mov     r10, cs:WPP_GLOBAL_Control
0x14003f295  lea     rcx, WPP_GLOBAL_Control
0x14003f29c  cmp     r10, rcx
0x14003f29f  jz      loc_14003F45C
0x14003f2a5  mov     edx, [r10+2Ch]
0x14003f2a9  test    dl, 20h
0x14003f2ac  jz      loc_14003F45C
0x14003f2b2  cmp     byte ptr [r10+29h], 2
0x14003f2b7  jb      loc_14003F45C
0x14003f2bd  mov     edx, 76h ; 'v'
0x14003f2c2  jmp     loc_14003F449
0x14003f2c7  mov     edx, 100h; unsigned __int64
0x14003f2cc  mov     r8d, 69526D56h; unsigned int
0x14003f2d2  lea     ecx, [rdx+10h]; unsigned __int64
0x14003f2d5  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14003f2da  mov     rbx, rax
0x14003f2dd  test    rax, rax
0x14003f2e0  jz      loc_14003F41D
0x14003f2e6  mov     rdi, [rsp+58h+arg_10]
0x14003f2eb  lea     rax, ??_7VMX_VOLUME_INFO@@6B@; const VMX_VOLUME_INFO::`vftable'
0x14003f2f2  mov     [rbx], rax
0x14003f2f5  lea     rcx, [rbx+48h]; pszDest
0x14003f2f9  mov     r12d, 1
0x14003f2ff  mov     [rbx+30h], rdi
0x14003f303  lea     r8, aGen; "gen"
0x14003f30a  mov     qword ptr [rbx+38h], 0
0x14003f312  mov     [rbx+40h], r12b
0x14003f316  lea     edx, [r12+1Fh]; cbDest
0x14003f31b  call    RtlStringCbCopyA
0x14003f320  lea     rcx, [rbx+79h]; pszDest
0x14003f324  mov     byte ptr [rbx+88h], 3
0x14003f32b  lea     r8, Str2; "ACTIVE"
0x14003f332  lea     edx, [r12+0Eh]; cbDest
0x14003f337  call    RtlStringCbCopyA
0x14003f33c  lea     rdx, [rbx+98h]; unsigned int *
0x14003f343  mov     rcx, rbp; this
0x14003f346  call    ?NextVolumeMinor@VMX_CONFIG@@QEAAXPEAK@Z; VMX_CONFIG::NextVolumeMinor(ulong *)
0x14003f34b  mov     rdx, 8000000000000000h; unsigned __int64
0x14003f355  mov     dword ptr [rbx+9Ch], 11h
0x14003f35f  mov     rcx, rbx; this
0x14003f362  mov     dword ptr [rbx+0C8h], 6
0x14003f36c  call    ?SetGptAttributes@VMX_VOLUME_INFO@@QEAAX_K@Z; VMX_VOLUME_INFO::SetGptAttributes(unsigned __int64)
0x14003f371  test    rsi, rsi
0x14003f374  jz      short loc_14003F3B5
0x14003f376  mov     rax, [rsi]
0x14003f379  sub     rax, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x14003f380  jnz     short loc_14003F38D
0x14003f382  mov     rax, [rsi+8]
0x14003f386  sub     rax, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data4; _GUID const GUID_NULL ...
0x14003f38d  test    rax, rax
0x14003f390  jz      short loc_14003F3B5
0x14003f392  movups  xmm0, xmmword ptr [rsi]
0x14003f395  movdqu  xmmword ptr [rbx+0E8h], xmm0
0x14003f39d  mov     [rdi+20h], r12w
0x14003f3a2  mov     [rdi+30h], rbx
0x14003f3a6  or      [rdi+40h], r12w
0x14003f3ab  xor     eax, eax
0x14003f3ad  mov     [r14], rdi
0x14003f3b0  jmp     loc_14003F45E
0x14003f3b5  lea     rcx, [rbx+0E8h]; Uuid
0x14003f3bc  call    cs:__imp_ExUuidCreate
0x14003f3c3  nop     dword ptr [rax+rax+00h]
0x14003f3c8  mov     esi, eax
0x14003f3ca  test    eax, eax
0x14003f3cc  jns     short loc_14003F39D
0x14003f3ce  mov     rcx, [rbx]
0x14003f3d1  mov     edx, r12d
0x14003f3d4  mov     rax, [rcx]
0x14003f3d7  mov     rcx, rbx
0x14003f3da  call    _guard_dispatch_icall
0x14003f3df  mov     r10, cs:WPP_GLOBAL_Control
0x14003f3e6  lea     rcx, WPP_GLOBAL_Control
0x14003f3ed  cmp     r10, rcx
0x14003f3f0  jz      short loc_14003F419
0x14003f3f2  mov     eax, [r10+2Ch]
0x14003f3f6  test    al, 20h
0x14003f3f8  jz      short loc_14003F419
0x14003f3fa  cmp     byte ptr [r10+29h], 2
0x14003f3ff  jb      short loc_14003F419
0x14003f401  mov     rcx, [r10+18h]
0x14003f405  lea     r8, WPP_ecea8329fd353f2ede86956965576228_Traceguids
0x14003f40c  mov     edx, 78h ; 'x'
0x14003f411  mov     r9d, esi
0x14003f414  call    WPP_SF_d
0x14003f419  mov     eax, esi
0x14003f41b  jmp     short loc_14003F45E
0x14003f41d  mov     r10, cs:WPP_GLOBAL_Control
0x14003f424  lea     rcx, WPP_GLOBAL_Control
0x14003f42b  mov     ebx, 0C000009Ah
0x14003f430  cmp     r10, rcx
0x14003f433  jz      short loc_14003F45C
0x14003f435  mov     eax, [r10+2Ch]
0x14003f439  test    al, 20h
0x14003f43b  jz      short loc_14003F45C
0x14003f43d  cmp     byte ptr [r10+29h], 2
0x14003f442  jb      short loc_14003F45C
0x14003f444  mov     edx, 77h ; 'w'
0x14003f449  mov     rcx, [r10+18h]
0x14003f44d  lea     r8, WPP_ecea8329fd353f2ede86956965576228_Traceguids
0x14003f454  mov     r9d, ebx
0x14003f457  call    WPP_SF_d
0x14003f45c  mov     eax, ebx
0x14003f45e  add     rsp, 28h
0x14003f462  pop     r14
0x14003f464  pop     r12
0x14003f466  pop     rdi
0x14003f467  pop     rsi
0x14003f468  pop     rbp
0x14003f469  pop     rbx
0x14003f46a  retn
```
