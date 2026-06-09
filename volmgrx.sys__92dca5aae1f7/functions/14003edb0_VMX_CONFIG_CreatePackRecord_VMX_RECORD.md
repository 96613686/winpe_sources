# VMX_CONFIG::CreatePackRecord(VMX_RECORD * *)

- ea: `0x14003edb0`
- end: `0x14003ef2f`
- name: `?CreatePackRecord@VMX_CONFIG@@QEAAJPEAPEAVVMX_RECORD@@@Z`
- size: `383`
- prototype: `__int64 __fastcall(VMX_CONFIG *__hidden this, struct VMX_RECORD **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400316d4`

## callees

- `0x140005f80`
- `0x1400099d8`
- `0x14001b9a0`
- `0x14003edb0`
- `0x14003f05c`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x14003ee66`
- `ntoskrnl!ExUuidCreate` at `0x14003ee66`

## pseudocode

```c
__int64 __fastcall VMX_CONFIG::CreatePackRecord(VMX_CONFIG *this, struct VMX_RECORD **a2)
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
    v5 = 128;
LABEL_18:
    WPP_SF_d(*((_QWORD *)v4 + 3), v5, WPP_ecea8329fd353f2ede86956965576228_Traceguids, v3);
    return v3;
  }
  v6 = VMX_ALLOCATED_OBJECT::operator new(120, 256, 1767009622);
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
    v5 = 129;
    goto LABEL_18;
  }
  v7 = v10;
  *(_QWORD *)v6 = &VMX_PACK_INFO::`vftable';
  *(_QWORD *)(v6 + 48) = v7;
  *(_QWORD *)(v6 + 56) = 0;
  *(_BYTE *)(v6 + 64) = 1;
  v8 = ExUuidCreate((UUID *)(v6 + 72));
  if ( v8 >= 0 )
  {
    *((_WORD *)v7 + 16) = 5;
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
        130,
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
0x14003edb0  mov     rax, rsp
0x14003edb3  mov     [rax+8], rbx
0x14003edb7  mov     [rax+18h], rsi
0x14003edbb  push    rdi
0x14003edbc  push    r14
0x14003edbe  push    r15
0x14003edc0  sub     rsp, 20h
0x14003edc4  mov     r14, rdx
0x14003edc7  mov     qword ptr [rdx], 0
0x14003edce  lea     rdx, [rax+10h]; struct VMX_RECORD **
0x14003edd2  mov     qword ptr [rax+10h], 0
0x14003edda  call    ?CreateRecord@VMX_CONFIG@@QEAAJPEAPEAVVMX_RECORD@@@Z; VMX_CONFIG::CreateRecord(VMX_RECORD * *)
0x14003eddf  mov     ebx, eax
0x14003ede1  test    eax, eax
0x14003ede3  jns     short loc_14003EE1C
0x14003ede5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003edec  lea     rdx, WPP_GLOBAL_Control
0x14003edf3  cmp     rcx, rdx
0x14003edf6  jz      loc_14003EF18
0x14003edfc  mov     edx, [rcx+2Ch]
0x14003edff  test    dl, 20h
0x14003ee02  jz      loc_14003EF18
0x14003ee08  cmp     byte ptr [rcx+29h], 2
0x14003ee0c  jb      loc_14003EF18
0x14003ee12  mov     edx, 80h
0x14003ee17  jmp     loc_14003EF05
0x14003ee1c  mov     edx, 100h; unsigned __int64
0x14003ee21  mov     ecx, 78h ; 'x'; unsigned __int64
0x14003ee26  mov     r8d, 69526D56h; unsigned int
0x14003ee2c  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14003ee31  mov     rbx, rax
0x14003ee34  test    rax, rax
0x14003ee37  jz      loc_14003EEDB
0x14003ee3d  mov     rdi, [rsp+38h+arg_8]
0x14003ee42  lea     rax, ??_7VMX_PACK_INFO@@6B@; const VMX_PACK_INFO::`vftable'
0x14003ee49  mov     [rbx], rax
0x14003ee4c  lea     rcx, [rbx+48h]; Uuid
0x14003ee50  mov     r15d, 1
0x14003ee56  mov     [rbx+30h], rdi
0x14003ee5a  mov     qword ptr [rbx+38h], 0
0x14003ee62  mov     [rbx+40h], r15b
0x14003ee66  call    cs:__imp_ExUuidCreate
0x14003ee6d  nop     dword ptr [rax+rax+00h]
0x14003ee72  mov     esi, eax
0x14003ee74  test    eax, eax
0x14003ee76  jns     short loc_14003EEC5
0x14003ee78  mov     rcx, [rbx]
0x14003ee7b  mov     edx, r15d
0x14003ee7e  mov     rax, [rcx]
0x14003ee81  mov     rcx, rbx
0x14003ee84  call    _guard_dispatch_icall
0x14003ee89  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ee90  lea     rdx, WPP_GLOBAL_Control
0x14003ee97  cmp     rcx, rdx
0x14003ee9a  jz      short loc_14003EEC1
0x14003ee9c  mov     eax, [rcx+2Ch]
0x14003ee9f  test    al, 20h
0x14003eea1  jz      short loc_14003EEC1
0x14003eea3  cmp     byte ptr [rcx+29h], 2
0x14003eea7  jb      short loc_14003EEC1
0x14003eea9  mov     rcx, [rcx+18h]
0x14003eead  lea     r8, WPP_ecea8329fd353f2ede86956965576228_Traceguids
0x14003eeb4  mov     edx, 82h
0x14003eeb9  mov     r9d, esi
0x14003eebc  call    WPP_SF_d
0x14003eec1  mov     eax, esi
0x14003eec3  jmp     short loc_14003EF1A
0x14003eec5  mov     word ptr [rdi+20h], 5
0x14003eecb  mov     [rdi+30h], rbx
0x14003eecf  or      [rdi+40h], r15w
0x14003eed4  xor     eax, eax
0x14003eed6  mov     [r14], rdi
0x14003eed9  jmp     short loc_14003EF1A
0x14003eedb  mov     rcx, cs:WPP_GLOBAL_Control
0x14003eee2  lea     rdx, WPP_GLOBAL_Control
0x14003eee9  mov     ebx, 0C000009Ah
0x14003eeee  cmp     rcx, rdx
0x14003eef1  jz      short loc_14003EF18
0x14003eef3  mov     eax, [rcx+2Ch]
0x14003eef6  test    al, 20h
0x14003eef8  jz      short loc_14003EF18
0x14003eefa  cmp     byte ptr [rcx+29h], 2
0x14003eefe  jb      short loc_14003EF18
0x14003ef00  mov     edx, 81h
0x14003ef05  mov     rcx, [rcx+18h]
0x14003ef09  lea     r8, WPP_ecea8329fd353f2ede86956965576228_Traceguids
0x14003ef10  mov     r9d, ebx
0x14003ef13  call    WPP_SF_d
0x14003ef18  mov     eax, ebx
0x14003ef1a  mov     rbx, [rsp+38h+arg_0]
0x14003ef1f  mov     rsi, [rsp+38h+arg_10]
0x14003ef24  add     rsp, 20h
0x14003ef28  pop     r15
0x14003ef2a  pop     r14
0x14003ef2c  pop     rdi
0x14003ef2d  retn
```
