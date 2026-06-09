# InvokeDeviceClassCallback

- ea: `0x14002b010`
- end: `0x14002b3b4`
- name: `InvokeDeviceClassCallback`
- size: `932`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14002aec4`

## callees

- `0x1400083c8`
- `0x1400088b4`
- `0x14000a6cc`
- `0x14000f664`
- `0x140014d50`
- `0x140014e00`
- `0x140026b6c`
- `0x14002b010`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002b203`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b203`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14002b08e`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14002b08e`
- `ntoskrnl!ZwQueryValueKey` at `0x14002b1b1`
- `ntoskrnl!ZwQueryValueKey` at `0x14002b1b1`
- `ntoskrnl!ZwClose` at `0x14002b10c`
- `ntoskrnl!ZwClose` at `0x14002b10c`
- `ntoskrnl!ExAllocatePool2` at `0x14002b181`
- `ntoskrnl!ExAllocatePool2` at `0x14002b181`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002b163`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002b163`

## pseudocode

```c
__int64 __fastcall InvokeDeviceClassCallback(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  int v3; // eax
  __int64 v4; // r12
  char v6; // bl
  char v7; // si
  char v8; // r14
  char v9; // r15
  struct _DEVICE_OBJECT *v10; // rcx
  char v11; // r13
  void *v12; // r14
  _DWORD *Pool2; // r14
  NTSTATUS v15; // eax
  int v16; // r12d
  unsigned int v17; // esi
  size_t v18; // r8
  int v19; // r15d
  int v20; // eax
  int v21; // edx
  unsigned int v22; // r14d
  int v23; // r9d
  int v24; // r8d
  size_t Size; // [rsp+30h] [rbp-48h]
  int v26; // [rsp+44h] [rbp-34h] BYREF
  int v27; // [rsp+48h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+4Ch] [rbp-2Ch] BYREF
  void *DeviceRegKey; // [rsp+50h] [rbp-28h] BYREF
  PVOID P; // [rsp+58h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-18h] BYREF
  char v32; // [rsp+C0h] [rbp+48h]
  char v34; // [rsp+D8h] [rbp+60h]

  v3 = *(_DWORD *)(a1 + 1228);
  v4 = (__int64)a3;
  P = 0;
  v6 = 0;
  v27 = 0;
  v26 = 0;
  *a2 = 0;
  *a3 = 0;
  if ( (v3 & 2) == 0 || (v12 = *(void **)(a1 + 1272)) == 0 )
  {
    v7 = *(_BYTE *)(a1 + 101);
    v8 = *(_BYTE *)(a1 + 102);
    v9 = 0;
    v10 = *(struct _DEVICE_OBJECT **)(a1 + 24);
    v11 = *(_BYTE *)(a1 + 100);
    DeviceRegKey = 0;
    v32 = v7;
    v34 = v8;
    if ( IoOpenDeviceRegistryKey(v10, 2u, 0x1F0000u, &DeviceRegKey) < 0 )
      goto LABEL_3;
    ResultLength = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"EnumeratorClass");
    Pool2 = (_DWORD *)ExAllocatePool2(256, 16, 1130525525);
    if ( Pool2 )
    {
      v15 = ZwQueryValueKey(DeviceRegKey, &DestinationString, KeyValuePartialInformation, Pool2, 0x10u, &ResultLength);
      v16 = 0;
      if ( v15 != -2147483643 )
        v16 = v15;
      if ( v16 < 0 )
      {
        v17 = 0;
        v19 = 0;
      }
      else
      {
        v17 = Pool2[2];
        v18 = v17;
        if ( v17 > 4 )
          v18 = 4;
        memmove(&v26, Pool2 + 3, v18);
        v19 = Pool2[1];
        v6 = v26;
      }
      ExFreePoolWithTag(Pool2, 0x43627355u);
    }
    else
    {
      v19 = 0;
      v16 = -1073741670;
      v17 = 0;
    }
    ZwClose(DeviceRegKey);
    if ( v16 < 0 || v17 < 3 )
    {
      v4 = (__int64)a3;
    }
    else
    {
      v4 = (__int64)a3;
      if ( v19 == 3 )
      {
        v7 = BYTE1(v26);
        v11 = v6;
        v8 = BYTE2(v26);
        v9 = 1;
LABEL_3:
        LODWORD(a2) = 0;
        while ( !(_DWORD)a2 )
        {
          if ( v9
            && v11 == (_BYTE)callbackFunctionTable
            && v7 == BYTE1(callbackFunctionTable)
            && v8 == BYTE2(callbackFunctionTable) )
          {
            v12 = &CdcCallback;
            if ( &CdcCallback )
              goto LABEL_32;
            break;
          }
          LODWORD(a2) = 1;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return 0;
        v23 = 15;
        LOBYTE(a2) = 4;
        v24 = 1;
        goto LABEL_44;
      }
    }
    v7 = v32;
    v9 = 0;
    v8 = v34;
    goto LABEL_3;
  }
LABEL_32:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_q(
      *(_QWORD *)(a1 + 1368),
      (_DWORD)a2,
      1,
      12,
      (__int64)WPP_e8749e7517b2302104950dba271a6a56_Traceguids,
      *(_QWORD *)(a1 + 32));
  }
  v20 = ((__int64 (__fastcall *)(__int64, _QWORD, PVOID *, int *, _QWORD, _QWORD))v12)(
          a1 + 96,
          *(_QWORD *)(a1 + 56),
          &P,
          &v27,
          *(_QWORD *)(a1 + 32),
          *(_QWORD *)(a1 + 24));
  v22 = v20;
  if ( v20 >= 0 )
  {
    LODWORD(a2) = (_DWORD)P;
    if ( !P || !v27 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 0;
      v23 = 14;
      LOBYTE(a2) = 2;
      v24 = 8;
LABEL_44:
      WPP_RECORDER_SF_(
        *(_QWORD *)(a1 + 1368),
        (_DWORD)a2,
        v24,
        v23,
        (__int64)WPP_e8749e7517b2302104950dba271a6a56_Traceguids);
      return 0;
    }
    return ProcessFunctionDescriptors(a1, P, v4);
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v21) = 4;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 1368),
        v21,
        1,
        13,
        (__int64)WPP_e8749e7517b2302104950dba271a6a56_Traceguids,
        v20);
    }
    LODWORD(Size) = *(unsigned __int16 *)(*(_QWORD *)(a1 + 48) + 2LL);
    RecordStartFailData(a1, v22, 0, -1610612726, 1179403074, *(void **)(a1 + 48), Size);
    return v22;
  }
}

```

## disassembly

```asm
0x14002b010  mov     [rsp-40h+arg_10], r8
0x14002b015  mov     [rsp-40h+arg_8], rdx
0x14002b01a  push    rbp
0x14002b01b  push    rbx
0x14002b01c  push    rsi
0x14002b01d  push    rdi
0x14002b01e  push    r12
0x14002b020  push    r13
0x14002b022  push    r14
0x14002b024  push    r15
0x14002b026  mov     rbp, rsp
0x14002b029  sub     rsp, 78h
0x14002b02d  mov     eax, [rcx+4CCh]
0x14002b033  mov     r12, r8
0x14002b036  xor     r8d, r8d
0x14002b039  mov     rdi, rcx
0x14002b03c  mov     [rbp+P], r8
0x14002b040  mov     ebx, r8d
0x14002b043  mov     [rbp+var_30], r8d
0x14002b047  mov     r13, rdx
0x14002b04a  mov     [rbp+var_34], ebx
0x14002b04d  mov     [rdx], r8
0x14002b050  lea     ecx, [r8+4]
0x14002b054  mov     [r12], r8d
0x14002b058  test    al, 2
0x14002b05a  jnz     loc_14002B138
0x14002b060  mov     sil, [rdi+65h]
0x14002b064  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x14002b068  mov     r14b, [rdi+66h]
0x14002b06c  mov     r15b, r8b
0x14002b06f  mov     rcx, [rdi+18h]; DeviceObject
0x14002b073  mov     edx, 2; DevInstKeyType
0x14002b078  mov     r13b, [rdi+64h]
0x14002b07c  mov     [rbp+DeviceRegKey], r8
0x14002b080  mov     r8d, 1F0000h; DesiredAccess
0x14002b086  mov     [rbp+arg_0], sil
0x14002b08a  mov     [rbp+arg_18], r14b
0x14002b08e  call    cs:__imp_IoOpenDeviceRegistryKey
0x14002b095  nop     dword ptr [rax+rax+00h]
0x14002b09a  xor     r8d, r8d
0x14002b09d  test    eax, eax
0x14002b09f  jns     loc_14002B14D
0x14002b0a5  mov     edx, r8d
0x14002b0a8  lea     r9, callbackFunctionTable
0x14002b0af  cmp     edx, 1
0x14002b0b2  jnb     short loc_14002B0E0
0x14002b0b4  mov     eax, edx
0x14002b0b6  lea     rcx, [rax+rax*2]
0x14002b0ba  test    r15b, r15b
0x14002b0bd  jnz     loc_14002B24E
0x14002b0c3  cmp     [r9+rcx*8+10h], r8b
0x14002b0c8  jnz     loc_14002B24E
0x14002b0ce  inc     edx
0x14002b0d0  jmp     short loc_14002B0AF
0x14002b0d2  mov     r14, [r9+rcx*8+8]
0x14002b0d7  test    r14, r14
0x14002b0da  jnz     loc_14002B273
0x14002b0e0  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002b0e7  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14002b0ee  jnz     loc_14002B38B
0x14002b0f4  xor     eax, eax
0x14002b0f6  add     rsp, 78h
0x14002b0fa  pop     r15
0x14002b0fc  pop     r14
0x14002b0fe  pop     r13
0x14002b100  pop     r12
0x14002b102  pop     rdi
0x14002b103  pop     rsi
0x14002b104  pop     rbx
0x14002b105  pop     rbp
0x14002b106  retn
0x14002b108  mov     rcx, [rbp+DeviceRegKey]; Handle
0x14002b10c  call    cs:__imp_ZwClose
0x14002b113  nop     dword ptr [rax+rax+00h]
0x14002b118  xor     r8d, r8d
0x14002b11b  test    r12d, r12d
0x14002b11e  jns     loc_14002B224
0x14002b124  mov     r12, [rbp+arg_10]
0x14002b128  mov     sil, [rbp+arg_0]
0x14002b12c  mov     r15b, r8b
0x14002b12f  mov     r14b, [rbp+arg_18]
0x14002b133  jmp     loc_14002B0A5
0x14002b138  mov     r14, [rdi+4F8h]
0x14002b13f  test    r14, r14
0x14002b142  jnz     loc_14002B27C
0x14002b148  jmp     loc_14002B060
0x14002b14d  xorps   xmm0, xmm0
0x14002b150  mov     [rbp+var_2C], r8d
0x14002b154  lea     rdx, aEnumeratorclas; "EnumeratorClass"
0x14002b15b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14002b15f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14002b163  call    cs:__imp_RtlInitUnicodeString
0x14002b16a  nop     dword ptr [rax+rax+00h]
0x14002b16f  mov     esi, 10h
0x14002b174  mov     r8d, 43627355h
0x14002b17a  mov     edx, esi
0x14002b17c  mov     ecx, 100h
0x14002b181  call    cs:__imp_ExAllocatePool2
0x14002b188  nop     dword ptr [rax+rax+00h]
0x14002b18d  mov     r14, rax
0x14002b190  test    rax, rax
0x14002b193  jz      short loc_14002B214
0x14002b195  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x14002b199  lea     rax, [rbp+var_2C]
0x14002b19d  mov     [rsp+78h+ResultLength], rax; ResultLength
0x14002b1a2  lea     r8d, [rsi-0Eh]; KeyValueInformationClass
0x14002b1a6  mov     r9, r14; KeyValueInformation
0x14002b1a9  mov     [rsp+78h+Length], esi; Length
0x14002b1ad  lea     rdx, [rbp+DestinationString]; ValueName
0x14002b1b1  call    cs:__imp_ZwQueryValueKey
0x14002b1b8  nop     dword ptr [rax+rax+00h]
0x14002b1bd  xor     r12d, r12d
0x14002b1c0  cmp     eax, 80000005h
0x14002b1c5  cmovnz  r12d, eax
0x14002b1c9  test    r12d, r12d
0x14002b1cc  js      short loc_14002B1F6
0x14002b1ce  mov     esi, [r14+8]
0x14002b1d2  lea     rdx, [r14+0Ch]; Src
0x14002b1d6  mov     ecx, 4
0x14002b1db  mov     r8d, esi
0x14002b1de  cmp     esi, ecx
0x14002b1e0  cmova   r8d, ecx; Size
0x14002b1e4  lea     rcx, [rbp+var_34]; void *
0x14002b1e8  call    memmove
0x14002b1ed  mov     r15d, [r14+4]
0x14002b1f1  mov     ebx, [rbp+var_34]
0x14002b1f4  jmp     short loc_14002B1FB
0x14002b1f6  xor     esi, esi
0x14002b1f8  xor     r15d, r15d
0x14002b1fb  mov     edx, 43627355h; Tag
0x14002b200  mov     rcx, r14; P
0x14002b203  call    cs:__imp_ExFreePoolWithTag
0x14002b20a  nop     dword ptr [rax+rax+00h]
0x14002b20f  jmp     loc_14002B108
0x14002b214  xor     r15d, r15d
0x14002b217  mov     r12d, 0C000009Ah
0x14002b21d  xor     esi, esi
0x14002b21f  jmp     loc_14002B108
0x14002b224  cmp     esi, 3
0x14002b227  jb      loc_14002B124
0x14002b22d  mov     r12, [rbp+arg_10]
0x14002b231  cmp     r15d, 3
0x14002b235  jnz     loc_14002B128
0x14002b23b  mov     sil, byte ptr [rbp+var_34+1]
0x14002b23f  mov     r13b, bl
0x14002b242  mov     r14b, byte ptr [rbp+var_34+2]
0x14002b246  mov     r15b, 1
0x14002b249  jmp     loc_14002B0A5
0x14002b24e  cmp     r13b, [r9+rcx*8]
0x14002b252  jnz     loc_14002B0CE
0x14002b258  cmp     sil, [r9+rcx*8+1]
0x14002b25d  jnz     loc_14002B0CE
0x14002b263  cmp     r14b, [r9+rcx*8+2]
0x14002b268  jz      loc_14002B0D2
0x14002b26e  jmp     loc_14002B0CE
0x14002b273  mov     r13, [rbp+arg_8]
0x14002b277  mov     ecx, 4
0x14002b27c  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002b283  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14002b28a  lea     rsi, WPP_e8749e7517b2302104950dba271a6a56_Traceguids
0x14002b291  jz      short loc_14002B2B9
0x14002b293  mov     rax, [rdi+20h]
0x14002b297  mov     r9d, 0Ch
0x14002b29d  mov     dl, cl
0x14002b29f  mov     [rsp+78h+ResultLength], rax
0x14002b2a4  mov     rcx, [rdi+558h]
0x14002b2ab  mov     qword ptr [rsp+78h+Length], rsi
0x14002b2b0  lea     r8d, [r9-0Bh]
0x14002b2b4  call    WPP_RECORDER_SF_q
0x14002b2b9  mov     rdx, [rdi+18h]
0x14002b2bd  lea     r9, [rbp+var_30]
0x14002b2c1  mov     [rsp+78h+ResultLength], rdx
0x14002b2c6  lea     r8, [rbp+P]
0x14002b2ca  mov     rdx, [rdi+20h]
0x14002b2ce  lea     rcx, [rdi+60h]
0x14002b2d2  mov     qword ptr [rsp+78h+Length], rdx
0x14002b2d7  mov     rax, r14
0x14002b2da  mov     rdx, [rdi+38h]
0x14002b2de  call    _guard_dispatch_icall
0x14002b2e3  mov     r14d, eax
0x14002b2e6  test    eax, eax
0x14002b2e8  jns     short loc_14002B349
0x14002b2ea  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14002b2f1  jz      short loc_14002B314
0x14002b2f3  mov     rcx, [rdi+558h]
0x14002b2fa  mov     r9d, 0Dh
0x14002b300  mov     dword ptr [rsp+78h+ResultLength], eax
0x14002b304  mov     dl, 4
0x14002b306  mov     qword ptr [rsp+78h+Length], rsi
0x14002b30b  lea     r8d, [r9-0Ch]
0x14002b30f  call    WPP_RECORDER_SF_d
0x14002b314  mov     rcx, [rdi+30h]
0x14002b318  mov     r9d, 0A000000Ah; int
0x14002b31e  xor     r8d, r8d; int
0x14002b321  mov     edx, r14d; int
0x14002b324  movzx   eax, word ptr [rcx+2]
0x14002b328  mov     dword ptr [rsp+78h+Size], eax; Size
0x14002b32c  mov     [rsp+78h+ResultLength], rcx; Src
0x14002b331  mov     rcx, rdi; int
0x14002b334  mov     [rsp+78h+Length], 464C4342h; int
0x14002b33c  call    RecordStartFailData
0x14002b341  mov     eax, r14d
0x14002b344  jmp     loc_14002B0F6
0x14002b349  mov     rdx, [rbp+P]; P
0x14002b34d  test    rdx, rdx
0x14002b350  jz      short loc_14002B370
0x14002b352  mov     r8d, [rbp+var_30]
0x14002b356  test    r8d, r8d
0x14002b359  jz      short loc_14002B370
0x14002b35b  mov     r9, r13
0x14002b35e  mov     qword ptr [rsp+78h+Length], r12; __int64
0x14002b363  mov     rcx, rdi; int
0x14002b366  call    ProcessFunctionDescriptors
0x14002b36b  jmp     loc_14002B0F6
0x14002b370  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14002b377  jz      loc_14002B0F4
0x14002b37d  mov     r9d, 0Eh
0x14002b383  mov     dl, 2
0x14002b385  lea     r8d, [r9-6]
0x14002b389  jmp     short loc_14002B39E
0x14002b38b  mov     r9d, 0Fh
0x14002b391  lea     rsi, WPP_e8749e7517b2302104950dba271a6a56_Traceguids
0x14002b398  mov     dl, 4
0x14002b39a  lea     r8d, [r9-0Eh]
0x14002b39e  mov     rcx, [rdi+558h]
0x14002b3a5  mov     qword ptr [rsp+78h+Length], rsi
0x14002b3aa  call    WPP_RECORDER_SF_
0x14002b3af  jmp     loc_14002B0F4
```
