# DllInitialize

- ea: `0x14002a080`
- end: `0x14002a330`
- name: `DllInitialize`
- size: `688`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140001008`
- `0x140001038`
- `0x140009c50`
- `0x14001bc5c`
- `0x14001bd08`
- `0x14002a044`
- `0x14002a080`
- `0x14002a804`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x14002a0c9`
- `ntoskrnl!EtwActivityIdControl` at `0x14002a0de`
- `ntoskrnl!EtwActivityIdControl` at `0x14002a251`
- `ntoskrnl!EtwActivityIdControl` at `0x14002a305`
- `ntoskrnl!EtwActivityIdControl` at `0x14002a0c9`
- `ntoskrnl!EtwActivityIdControl` at `0x14002a0de`
- `ntoskrnl!EtwActivityIdControl` at `0x14002a251`
- `ntoskrnl!EtwActivityIdControl` at `0x14002a305`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002a199`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002a199`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a1ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a1ca`
- `ntoskrnl!ExAllocatePool2` at `0x14002a161`
- `ntoskrnl!ExAllocatePool2` at `0x14002a161`
- `HAL!KeQueryPerformanceCounter` at `0x14002a26d`
- `HAL!KeQueryPerformanceCounter` at `0x14002a26d`

## string_xrefs

- `0x14002a0f0`: `DllInitialize`

## pseudocode

```c
__int64 __fastcall DllInitialize(PCUNICODE_STRING SourceString)
{
  __int64 v2; // rcx
  __int64 Length; // rdx
  int v4; // ebx
  __int16 v5; // di
  __int64 v6; // rcx
  __int64 v7; // rcx
  int v9; // [rsp+30h] [rbp-79h] BYREF
  __int64 v10; // [rsp+38h] [rbp-71h] BYREF
  GUID ActivityId; // [rsp+40h] [rbp-69h] BYREF
  GUID v12; // [rsp+50h] [rbp-59h] BYREF
  int v13; // [rsp+60h] [rbp-49h]
  _BYTE v14[32]; // [rsp+70h] [rbp-39h] BYREF
  const char *v15; // [rsp+90h] [rbp-19h]
  __int64 v16; // [rsp+98h] [rbp-11h]
  int *v17; // [rsp+A0h] [rbp-9h]
  __int64 v18; // [rsp+A8h] [rbp-1h]
  __int64 *v19; // [rsp+B0h] [rbp+7h]
  __int64 v20; // [rsp+B8h] [rbp+Fh]

  ActivityId = 0;
  v13 = 0;
  v12 = 0;
  _security_init_cookie();
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation();
  EtwActivityIdControl(5u, &ActivityId);
  EtwActivityIdControl(1u, &v12);
  if ( (unsigned int)dword_140011000 > 4 && (unsigned __int8)tlgKeywordOn() )
  {
    v15 = "DllInitialize";
    v16 = 14;
    v18 = 2;
    LOWORD(v9) = 125;
    v17 = &v9;
    tlgWriteTransfer_EtwWriteTransfer(v2, byte_14000E599, &v12, &ActivityId, 4, v14, v9);
  }
  Length = SourceString->Length;
  LOBYTE(v13) = 1;
  WinHvpRegistryPath.Buffer = (PWSTR)ExAllocatePool2(64, Length, 1433815127);
  if ( !WinHvpRegistryPath.Buffer )
  {
    v4 = -1073741670;
    v5 = 133;
LABEL_8:
    if ( WinHvpRegistryPath.Buffer )
    {
      ExFreePoolWithTag(WinHvpRegistryPath.Buffer, 0x55764857u);
      WinHvpRegistryPath.Buffer = 0;
    }
    if ( (_BYTE)v13 )
    {
      if ( (unsigned int)dword_140011000 > 2 && (unsigned __int8)tlgKeywordOn() )
      {
        v15 = "DllInitialize";
        v17 = &v9;
        v16 = 14;
        v19 = &v10;
        LOWORD(v9) = v5;
        v18 = 2;
        LODWORD(v10) = v4;
        v20 = 4;
        tlgWriteTransfer_EtwWriteTransfer(v6, byte_14000E523, &v12, 0, 5, v14, v9);
      }
      EtwActivityIdControl(2u, &ActivityId);
      LOBYTE(v13) = 0;
    }
    TraceLoggingUnregister_EtwUnregister();
    return (unsigned int)v4;
  }
  WinHvpRegistryPath.MaximumLength = SourceString->Length;
  RtlCopyUnicodeString(&WinHvpRegistryPath, SourceString);
  v4 = WinHvpInitialize();
  if ( v4 < 0 )
  {
    v5 = 140;
    goto LABEL_8;
  }
  qword_140016060 = KeQueryPerformanceCounter(0).QuadPart;
  if ( (_BYTE)v13 )
  {
    if ( (unsigned int)dword_140011000 > 4 && (unsigned __int8)tlgKeywordOn() )
    {
      v15 = "DllInitialize";
      v16 = 14;
      v18 = 2;
      LOWORD(v9) = 148;
      v20 = 8;
      v17 = &v9;
      v10 = qword_140016060;
      v19 = &v10;
      tlgWriteTransfer_EtwWriteTransfer(v7, byte_14000E559, &v12, 0, 5, v14, v9);
    }
    EtwActivityIdControl(2u, &ActivityId);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14002a080  push    rbp
0x14002a082  push    rbx
0x14002a083  push    rsi
0x14002a084  push    rdi
0x14002a085  push    r13
0x14002a087  push    r14
0x14002a089  lea     rbp, [rsp-2Fh]
0x14002a08e  sub     rsp, 0D8h
0x14002a095  mov     rax, cs:__security_cookie
0x14002a09c  xor     rax, rsp
0x14002a09f  mov     [rbp+57h+var_40], rax
0x14002a0a3  xorps   xmm0, xmm0
0x14002a0a6  xor     eax, eax
0x14002a0a8  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x14002a0ac  mov     [rbp+57h+var_A0], eax
0x14002a0af  mov     rbx, rcx
0x14002a0b2  movups  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x14002a0b6  call    __security_init_cookie
0x14002a0bb  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x14002a0c0  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x14002a0c4  mov     ecx, 5; ControlCode
0x14002a0c9  call    cs:__imp_EtwActivityIdControl
0x14002a0d0  nop     dword ptr [rax+rax+00h]
0x14002a0d5  lea     rdx, [rbp+57h+var_B0]; ActivityId
0x14002a0d9  mov     ecx, 1; ControlCode
0x14002a0de  call    cs:__imp_EtwActivityIdControl
0x14002a0e5  nop     dword ptr [rax+rax+00h]
0x14002a0ea  mov     eax, cs:dword_140011000
0x14002a0f0  lea     r13, aDllinitialize; "DllInitialize"
0x14002a0f7  xor     esi, esi
0x14002a0f9  lea     r14d, [rsi+2]
0x14002a0fd  cmp     eax, 4
0x14002a100  jbe     short loc_14002A14F
0x14002a102  call    _tlgKeywordOn
0x14002a107  test    al, al
0x14002a109  jz      short loc_14002A14F
0x14002a10b  mov     [rbp+57h+var_70], r13
0x14002a10f  mov     [rbp+57h+var_68], 0Eh
0x14002a117  lea     eax, [rsi+7Dh]
0x14002a11a  mov     [rbp+57h+var_58], r14
0x14002a11e  mov     word ptr [rbp+57h+var_D0], ax
0x14002a122  lea     r9, [rbp+57h+ActivityId]
0x14002a126  lea     rax, [rbp+57h+var_D0]
0x14002a12a  mov     [rbp+57h+var_60], rax
0x14002a12e  lea     r8, [rbp+57h+var_B0]
0x14002a132  lea     rax, [rbp+57h+var_90]
0x14002a136  mov     [rsp+100h+var_D8], rax
0x14002a13b  lea     rdx, byte_14000E599
0x14002a142  mov     [rsp+100h+var_E0], 4
0x14002a14a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14002a14f  movzx   edx, word ptr [rbx]
0x14002a152  mov     ecx, 40h ; '@'
0x14002a157  mov     r8d, 55764857h
0x14002a15d  mov     byte ptr [rbp+57h+var_A0], 1
0x14002a161  call    cs:__imp_ExAllocatePool2
0x14002a168  nop     dword ptr [rax+rax+00h]
0x14002a16d  mov     cs:WinHvpRegistryPath.Buffer, rax
0x14002a174  test    rax, rax
0x14002a177  jnz     short loc_14002A185
0x14002a179  mov     ebx, 0C000009Ah
0x14002a17e  mov     edi, 85h
0x14002a183  jmp     short loc_14002A1B9
0x14002a185  movzx   eax, word ptr [rbx]
0x14002a188  lea     rcx, WinHvpRegistryPath; DestinationString
0x14002a18f  mov     rdx, rbx; SourceString
0x14002a192  mov     cs:WinHvpRegistryPath.MaximumLength, ax
0x14002a199  call    cs:__imp_RtlCopyUnicodeString
0x14002a1a0  nop     dword ptr [rax+rax+00h]
0x14002a1a5  call    WinHvpInitialize
0x14002a1aa  mov     ebx, eax
0x14002a1ac  test    eax, eax
0x14002a1ae  jns     loc_14002A26B
0x14002a1b4  mov     edi, 8Ch
0x14002a1b9  mov     rcx, cs:WinHvpRegistryPath.Buffer; P
0x14002a1c0  test    rcx, rcx
0x14002a1c3  jz      short loc_14002A1DD
0x14002a1c5  mov     edx, 55764857h; Tag
0x14002a1ca  call    cs:__imp_ExFreePoolWithTag
0x14002a1d1  nop     dword ptr [rax+rax+00h]
0x14002a1d6  mov     cs:WinHvpRegistryPath.Buffer, rsi
0x14002a1dd  cmp     byte ptr [rbp+57h+var_A0], sil
0x14002a1e1  jz      short loc_14002A261
0x14002a1e3  mov     eax, cs:dword_140011000
0x14002a1e9  cmp     eax, r14d
0x14002a1ec  jbe     short loc_14002A24A
0x14002a1ee  call    _tlgKeywordOn
0x14002a1f3  test    al, al
0x14002a1f5  jz      short loc_14002A24A
0x14002a1f7  lea     rax, [rbp+57h+var_D0]
0x14002a1fb  mov     [rbp+57h+var_70], r13
0x14002a1ff  mov     [rbp+57h+var_60], rax
0x14002a203  lea     r8, [rbp+57h+var_B0]
0x14002a207  lea     rax, [rbp+57h+var_C8]
0x14002a20b  mov     [rbp+57h+var_68], 0Eh
0x14002a213  mov     [rbp+57h+var_50], rax
0x14002a217  lea     rdx, byte_14000E523
0x14002a21e  lea     rax, [rbp+57h+var_90]
0x14002a222  mov     word ptr [rbp+57h+var_D0], di
0x14002a226  mov     [rsp+100h+var_D8], rax
0x14002a22b  xor     r9d, r9d
0x14002a22e  mov     [rsp+100h+var_E0], 5
0x14002a236  mov     [rbp+57h+var_58], r14
0x14002a23a  mov     dword ptr [rbp+57h+var_C8], ebx
0x14002a23d  mov     [rbp+57h+var_48], 4
0x14002a245  call    _tlgWriteTransfer_EtwWriteTransfer
0x14002a24a  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x14002a24e  mov     ecx, r14d; ControlCode
0x14002a251  call    cs:__imp_EtwActivityIdControl
0x14002a258  nop     dword ptr [rax+rax+00h]
0x14002a25d  mov     byte ptr [rbp+57h+var_A0], sil
0x14002a261  call    TraceLoggingUnregister_EtwUnregister
0x14002a266  jmp     loc_14002A311
0x14002a26b  xor     ecx, ecx; PerformanceFrequency
0x14002a26d  call    cs:__imp_KeQueryPerformanceCounter
0x14002a274  nop     dword ptr [rax+rax+00h]
0x14002a279  mov     cs:qword_140016060, rax
0x14002a280  cmp     byte ptr [rbp+57h+var_A0], sil
0x14002a284  jz      loc_14002A311
0x14002a28a  mov     eax, cs:dword_140011000
0x14002a290  cmp     eax, 4
0x14002a293  jbe     short loc_14002A2FE
0x14002a295  call    _tlgKeywordOn
0x14002a29a  test    al, al
0x14002a29c  jz      short loc_14002A2FE
0x14002a29e  mov     [rbp+57h+var_70], r13
0x14002a2a2  mov     [rbp+57h+var_68], 0Eh
0x14002a2aa  mov     eax, 94h
0x14002a2af  mov     [rbp+57h+var_58], r14
0x14002a2b3  mov     word ptr [rbp+57h+var_D0], ax
0x14002a2b7  lea     r8, [rbp+57h+var_B0]
0x14002a2bb  lea     rax, [rbp+57h+var_D0]
0x14002a2bf  mov     [rbp+57h+var_48], 8
0x14002a2c7  mov     [rbp+57h+var_60], rax
0x14002a2cb  lea     rdx, byte_14000E559
0x14002a2d2  mov     rax, cs:qword_140016060
0x14002a2d9  xor     r9d, r9d
0x14002a2dc  mov     [rbp+57h+var_C8], rax
0x14002a2e0  lea     rax, [rbp+57h+var_C8]
0x14002a2e4  mov     [rbp+57h+var_50], rax
0x14002a2e8  lea     rax, [rbp+57h+var_90]
0x14002a2ec  mov     [rsp+100h+var_D8], rax
0x14002a2f1  mov     [rsp+100h+var_E0], 5
0x14002a2f9  call    _tlgWriteTransfer_EtwWriteTransfer
0x14002a2fe  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x14002a302  mov     ecx, r14d; ControlCode
0x14002a305  call    cs:__imp_EtwActivityIdControl
0x14002a30c  nop     dword ptr [rax+rax+00h]
0x14002a311  mov     eax, ebx
0x14002a313  mov     rcx, [rbp+57h+var_40]
0x14002a317  xor     rcx, rsp; StackCookie
0x14002a31a  call    __security_check_cookie
0x14002a31f  add     rsp, 0D8h
0x14002a326  pop     r14
0x14002a328  pop     r13
0x14002a32a  pop     rdi
0x14002a32b  pop     rsi
0x14002a32c  pop     rbx
0x14002a32d  pop     rbp
0x14002a32e  retn
```
