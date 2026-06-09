# IsCallerTermsrvService

- ea: `0x14000acac`
- end: `0x14000ae3b`
- name: `IsCallerTermsrvService`
- size: `399`
- prototype: `__int64 __fastcall(_BYTE *, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x14000af20`

## callees

- `0x14000173c`
- `0x1400017e8`
- `0x14000abb4`
- `0x14000acac`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000ad14`
- `ntoskrnl!ExAllocatePool2` at `0x14000ad14`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ade8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ade8`
- `ntoskrnl!RtlCheckTokenMembership` at `0x14000ad9d`
- `ntoskrnl!RtlCheckTokenMembership` at `0x14000ad9d`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14000acfb`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14000acfb`

## pseudocode

```c
__int64 __fastcall IsCallerTermsrvService(_BYTE *a1, int a2, int a3)
{
  ULONG v4; // eax
  void *Pool2; // rax
  int v6; // edx
  int v7; // r8d
  void *v8; // rsi
  int v9; // edx
  int v10; // r8d
  int v11; // edx
  int v12; // ebx
  int v13; // r8d
  char v15; // [rsp+80h] [rbp+8h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      43,
      (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
  *a1 = 0;
  v4 = RtlLengthRequiredSid(6u);
  Pool2 = (void *)ExAllocatePool2(256, v4, 1767142228);
  v8 = Pool2;
  if ( Pool2 )
  {
    InitializeServiceSid(Pool2);
    v15 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        v10,
        41,
        (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
    *a1 = 0;
    v12 = RtlCheckTokenMembership(0, v8, &v15);
    if ( v12 >= 0 )
      *a1 = v15;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        v13,
        42,
        (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
    ExFreePoolWithTag(v8, 0x69547354u);
  }
  else
  {
    v12 = -1073741670;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      v7,
      44,
      (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000acac  mov     [rsp+arg_8], rbx
0x14000acb1  mov     [rsp+arg_10], rbp
0x14000acb6  push    rsi
0x14000acb7  push    rdi
0x14000acb8  push    r14
0x14000acba  sub     rsp, 60h
0x14000acbe  mov     rdi, rcx
0x14000acc1  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000acc8  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000accf  lea     r14, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x14000acd6  jz      short loc_14000ACF3
0x14000acd8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000acdf  mov     r9d, 2Bh ; '+'
0x14000ace5  mov     [rsp+78h+var_58], r14
0x14000acea  mov     rcx, [rcx+40h]
0x14000acee  call    WPP_RECORDER_SF_s
0x14000acf3  mov     ecx, 6; SubAuthorityCount
0x14000acf8  mov     byte ptr [rdi], 0
0x14000acfb  call    cs:__imp_RtlLengthRequiredSid
0x14000ad02  nop     dword ptr [rax+rax+00h]
0x14000ad07  mov     edx, eax
0x14000ad09  mov     ecx, 100h
0x14000ad0e  mov     r8d, 69547354h
0x14000ad14  call    cs:__imp_ExAllocatePool2
0x14000ad1b  nop     dword ptr [rax+rax+00h]
0x14000ad20  mov     rsi, rax
0x14000ad23  test    rax, rax
0x14000ad26  jz      loc_14000ADF6
0x14000ad2c  lea     rdx, [rsp+78h+var_38]
0x14000ad31  mov     [rsp+78h+var_38], 1A963466h
0x14000ad39  mov     rcx, rax; Sid
0x14000ad3c  mov     [rsp+78h+var_34], 5CF1AAB9h
0x14000ad44  mov     [rsp+78h+var_30], 0F8123019h
0x14000ad4c  mov     [rsp+78h+var_2C], 7448CE95h
0x14000ad54  mov     [rsp+78h+var_28], 304EFDA0h
0x14000ad5c  call    InitializeServiceSid
0x14000ad61  mov     [rsp+78h+arg_0], 0
0x14000ad69  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000ad70  jz      short loc_14000AD8D
0x14000ad72  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ad79  mov     r9d, 29h ; ')'
0x14000ad7f  mov     [rsp+78h+var_58], r14
0x14000ad84  mov     rcx, [rcx+40h]
0x14000ad88  call    WPP_RECORDER_SF_s
0x14000ad8d  lea     r8, [rsp+78h+arg_0]
0x14000ad95  mov     byte ptr [rdi], 0
0x14000ad98  mov     rdx, rsi
0x14000ad9b  xor     ecx, ecx
0x14000ad9d  call    cs:__imp_RtlCheckTokenMembership
0x14000ada4  nop     dword ptr [rax+rax+00h]
0x14000ada9  mov     ebx, eax
0x14000adab  test    eax, eax
0x14000adad  js      short loc_14000ADB8
0x14000adaf  mov     al, [rsp+78h+arg_0]
0x14000adb6  mov     [rdi], al
0x14000adb8  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000adbf  jz      short loc_14000ADE0
0x14000adc1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000adc8  mov     r9d, 2Ah ; '*'
0x14000adce  mov     [rsp+78h+var_48], ebx
0x14000add2  mov     [rsp+78h+var_58], r14
0x14000add7  mov     rcx, [rcx+40h]
0x14000addb  call    WPP_RECORDER_SF_sD
0x14000ade0  mov     edx, 69547354h; Tag
0x14000ade5  mov     rcx, rsi; P
0x14000ade8  call    cs:__imp_ExFreePoolWithTag
0x14000adef  nop     dword ptr [rax+rax+00h]
0x14000adf4  jmp     short loc_14000ADFB
0x14000adf6  mov     ebx, 0C000009Ah
0x14000adfb  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000ae02  jz      short loc_14000AE23
0x14000ae04  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae0b  mov     r9d, 2Ch ; ','
0x14000ae11  mov     [rsp+78h+var_48], ebx
0x14000ae15  mov     [rsp+78h+var_58], r14
0x14000ae1a  mov     rcx, [rcx+40h]
0x14000ae1e  call    WPP_RECORDER_SF_sD
0x14000ae23  lea     r11, [rsp+78h+var_18]
0x14000ae28  mov     eax, ebx
0x14000ae2a  mov     rbx, [r11+28h]
0x14000ae2e  mov     rbp, [r11+30h]
0x14000ae32  mov     rsp, r11
0x14000ae35  pop     r14
0x14000ae37  pop     rdi
0x14000ae38  pop     rsi
0x14000ae39  retn
```
