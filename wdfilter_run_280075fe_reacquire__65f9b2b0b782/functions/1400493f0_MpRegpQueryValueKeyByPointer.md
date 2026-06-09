# MpRegpQueryValueKeyByPointer

- ea: `0x1400493f0`
- end: `0x14004967d`
- name: `MpRegpQueryValueKeyByPointer`
- size: `653`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14004a930`
- `0x14004b990`

## callees

- `0x1400026c0`
- `0x1400051bc`
- `0x1400118d0`
- `0x1400493f0`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x14004944a`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14004944a`
- `ntoskrnl!ZwQueryValueKey` at `0x140049504`
- `ntoskrnl!ZwQueryValueKey` at `0x14004961b`
- `ntoskrnl!ZwQueryValueKey` at `0x140049504`
- `ntoskrnl!ZwQueryValueKey` at `0x14004961b`
- `ntoskrnl!ZwClose` at `0x14004947d`
- `ntoskrnl!ZwClose` at `0x14004947d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004949b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004957d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004949b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004957d`

## pseudocode

```c
__int64 __fastcall MpRegpQueryValueKeyByPointer(void *a1, struct _UNICODE_STRING *a2, ULONG *a3, _QWORD *a4)
{
  void *PoolWithTag; // rbx
  ULONG v8; // esi
  NTSTATUS v9; // edi
  NTSTATUS v11; // eax
  __int64 v12; // rdx
  int ObjectType; // [rsp+20h] [rbp-78h]
  HANDLE KeyHandle; // [rsp+40h] [rbp-58h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-50h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  PoolWithTag = 0;
  v8 = 512;
  v9 = ObOpenObjectByPointer(a1, 0x200u, 0, 0x20019u, 0, 0, &KeyHandle);
  if ( v9 >= 0 )
  {
    PoolWithTag = (void *)MpAllocatePoolWithTag(1, 512, 1450332237);
    if ( !PoolWithTag )
    {
      v9 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v12 = 11;
        ObjectType = -1073741670;
        goto LABEL_22;
      }
      goto LABEL_3;
    }
    v11 = ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, PoolWithTag, 0x200u, &ResultLength);
    v9 = v11;
    if ( v11 == -1073741789 || v11 == -2147483643 )
    {
      v8 = ResultLength;
      ExFreePoolWithTag(PoolWithTag, 0x5672504Du);
      PoolWithTag = (void *)MpAllocatePoolWithTag(1, v8, 1450332237);
      if ( !PoolWithTag )
      {
        v9 = -1073741670;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v12 = 12;
          ObjectType = -1073741670;
          goto LABEL_22;
        }
        goto LABEL_3;
      }
      v9 = ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, PoolWithTag, v8, &ResultLength);
    }
    if ( v9 >= 0 )
    {
      *a3 = v8;
      v9 = 0;
      *a4 = PoolWithTag;
      PoolWithTag = 0;
      goto LABEL_3;
    }
    if ( v9 != -1073741772
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v12 = 13;
LABEL_16:
      _mm_lfence();
      ObjectType = v9;
LABEL_22:
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        v12,
        WPP_0bb7950fbf1c3ce6de4fbf0752af6f2f_Traceguids,
        KeGetCurrentThread(),
        ObjectType);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v12 = 10;
    goto LABEL_16;
  }
LABEL_3:
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0x5672504Du);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400493f0  push    rbx
0x1400493f2  push    rbp
0x1400493f3  push    rsi
0x1400493f4  push    rdi
0x1400493f5  push    r12
0x1400493f7  push    r14
0x1400493f9  push    r15
0x1400493fb  sub     rsp, 60h
0x1400493ff  mov     rax, cs:__security_cookie
0x140049406  xor     rax, rsp
0x140049409  mov     [rsp+98h+var_48], rax
0x14004940e  xor     r12d, r12d
0x140049411  lea     rax, [rsp+98h+KeyHandle]
0x140049416  mov     [rsp+98h+Handle], rax; Handle
0x14004941b  mov     r15, r9
0x14004941e  mov     r14, r8
0x140049421  mov     [rsp+98h+KeyHandle], r12
0x140049426  mov     rbp, rdx
0x140049429  mov     [rsp+98h+ResultLength], r12d
0x14004942e  mov     ebx, r12d
0x140049431  mov     esi, 200h
0x140049436  mov     [rsp+98h+AccessMode], bl; AccessMode
0x14004943a  mov     r9d, 20019h; DesiredAccess
0x140049440  xor     r8d, r8d; PassedAccessState
0x140049443  mov     [rsp+98h+ObjectType], r12; ObjectType
0x140049448  mov     edx, esi; HandleAttributes
0x14004944a  call    cs:__imp_ObOpenObjectByPointer
0x140049451  nop     dword ptr [rax+rax+00h]
0x140049456  mov     edi, eax
0x140049458  test    eax, eax
0x14004945a  jns     short loc_1400494C6
0x14004945c  mov     rcx, cs:WPP_GLOBAL_Control
0x140049463  lea     rax, WPP_GLOBAL_Control
0x14004946a  cmp     rcx, rax
0x14004946d  jnz     loc_14004962E
0x140049473  mov     rcx, [rsp+98h+KeyHandle]; Handle
0x140049478  test    rcx, rcx
0x14004947b  jz      short loc_14004948E
0x14004947d  call    cs:__imp_ZwClose
0x140049484  nop     dword ptr [rax+rax+00h]
0x140049489  mov     [rsp+98h+KeyHandle], r12
0x14004948e  test    rbx, rbx
0x140049491  jz      short loc_1400494A7
0x140049493  mov     edx, 5672504Dh; Tag
0x140049498  mov     rcx, rbx; P
0x14004949b  call    cs:__imp_ExFreePoolWithTag
0x1400494a2  nop     dword ptr [rax+rax+00h]
0x1400494a7  mov     eax, edi
0x1400494a9  mov     rcx, [rsp+98h+var_48]
0x1400494ae  xor     rcx, rsp; StackCookie
0x1400494b1  call    __security_check_cookie
0x1400494b6  add     rsp, 60h
0x1400494ba  pop     r15
0x1400494bc  pop     r14
0x1400494be  pop     r12
0x1400494c0  pop     rdi
0x1400494c1  pop     rsi
0x1400494c2  pop     rbp
0x1400494c3  pop     rbx
0x1400494c4  retn
0x1400494c6  mov     r8d, 5672504Dh
0x1400494cc  mov     rdx, rsi
0x1400494cf  mov     ecx, 1
0x1400494d4  call    MpAllocatePoolWithTag
0x1400494d9  mov     rbx, rax
0x1400494dc  test    rax, rax
0x1400494df  jz      loc_140049643
0x1400494e5  mov     rcx, [rsp+98h+KeyHandle]; KeyHandle
0x1400494ea  lea     rax, [rsp+98h+ResultLength]
0x1400494ef  mov     qword ptr [rsp+98h+AccessMode], rax; ResultLength
0x1400494f4  mov     r9, rbx; KeyValueInformation
0x1400494f7  mov     r8d, 2; KeyValueInformationClass
0x1400494fd  mov     dword ptr [rsp+98h+ObjectType], esi; Length
0x140049501  mov     rdx, rbp; ValueName
0x140049504  call    cs:__imp_ZwQueryValueKey
0x14004950b  nop     dword ptr [rax+rax+00h]
0x140049510  mov     edi, eax
0x140049512  cmp     eax, 0C0000023h
0x140049517  jz      short loc_140049571
0x140049519  cmp     eax, 80000005h
0x14004951e  jz      short loc_140049571
0x140049520  test    edi, edi
0x140049522  jns     short loc_140049560
0x140049524  cmp     edi, 0C0000034h
0x14004952a  jz      loc_140049473
0x140049530  mov     rcx, cs:WPP_GLOBAL_Control
0x140049537  lea     rax, WPP_GLOBAL_Control
0x14004953e  cmp     rcx, rax
0x140049541  jz      loc_140049473
0x140049547  mov     eax, [rcx+2Ch]
0x14004954a  test    al, 1
0x14004954c  jz      loc_140049473
0x140049552  mov     edx, 0Dh
0x140049557  lfence
0x14004955a  mov     dword ptr [rsp+98h+ObjectType], edi
0x14004955e  jmp     short loc_1400495D7
0x140049560  mov     [r14], esi
0x140049563  mov     edi, r12d
0x140049566  mov     [r15], rbx
0x140049569  mov     rbx, r12
0x14004956c  jmp     loc_140049473
0x140049571  mov     esi, [rsp+98h+ResultLength]
0x140049575  mov     edx, 5672504Dh; Tag
0x14004957a  mov     rcx, rbx; P
0x14004957d  call    cs:__imp_ExFreePoolWithTag
0x140049584  nop     dword ptr [rax+rax+00h]
0x140049589  mov     edx, esi
0x14004958b  mov     ecx, 1
0x140049590  mov     r8d, 5672504Dh
0x140049596  call    MpAllocatePoolWithTag
0x14004959b  mov     rbx, rax
0x14004959e  test    rax, rax
0x1400495a1  jnz     short loc_1400495FC
0x1400495a3  mov     edi, 0C000009Ah
0x1400495a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400495af  lea     rax, WPP_GLOBAL_Control
0x1400495b6  cmp     rcx, rax
0x1400495b9  jz      loc_140049473
0x1400495bf  mov     eax, [rcx+2Ch]
0x1400495c2  test    al, 1
0x1400495c4  jz      loc_140049473
0x1400495ca  mov     edx, 0Ch
0x1400495cf  mov     dword ptr [rsp+98h+ObjectType], 0C000009Ah
0x1400495d7  mov     r9, gs:188h
0x1400495e0  lea     r8, WPP_0bb7950fbf1c3ce6de4fbf0752af6f2f_Traceguids
0x1400495e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400495ee  mov     rcx, [rcx+18h]
0x1400495f2  call    WPP_SF_qD
0x1400495f7  jmp     loc_140049473
0x1400495fc  mov     rcx, [rsp+98h+KeyHandle]; KeyHandle
0x140049601  lea     rax, [rsp+98h+ResultLength]
0x140049606  mov     qword ptr [rsp+98h+AccessMode], rax; ResultLength
0x14004960b  mov     r9, rbx; KeyValueInformation
0x14004960e  mov     r8d, 2; KeyValueInformationClass
0x140049614  mov     dword ptr [rsp+98h+ObjectType], esi; Length
0x140049618  mov     rdx, rbp; ValueName
0x14004961b  call    cs:__imp_ZwQueryValueKey
0x140049622  nop     dword ptr [rax+rax+00h]
0x140049627  mov     edi, eax
0x140049629  jmp     loc_140049520
0x14004962e  mov     eax, [rcx+2Ch]
0x140049631  test    al, 1
0x140049633  jz      loc_140049473
0x140049639  mov     edx, 0Ah
0x14004963e  jmp     loc_140049557
0x140049643  mov     edi, 0C000009Ah
0x140049648  mov     rcx, cs:WPP_GLOBAL_Control
0x14004964f  lea     rax, WPP_GLOBAL_Control
0x140049656  cmp     rcx, rax
0x140049659  jz      loc_140049473
0x14004965f  mov     ecx, [rcx+2Ch]
0x140049662  test    cl, 1
0x140049665  jz      loc_140049473
0x14004966b  mov     edx, 0Bh
0x140049670  mov     dword ptr [rsp+98h+ObjectType], 0C000009Ah
0x140049678  jmp     loc_1400495D7
```
