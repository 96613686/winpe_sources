# WerpSendWersvcMessage

- ea: `0x1400011a0`
- end: `0x14000135f`
- name: `WerpSendWersvcMessage`
- size: `447`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140001368`

## callees

- `0x1400011a0`
- `0x14000ce68`
- `0x14000cfa8`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000133b`
- `ntoskrnl!DbgPrintEx` at `0x14000133b`
- `ntoskrnl!ZwAlpcSendWaitReceivePort` at `0x1400012ed`
- `ntoskrnl!ZwAlpcSendWaitReceivePort` at `0x1400012ed`
- `ntoskrnl!ZwAlpcConnectPort` at `0x1400012a4`
- `ntoskrnl!ZwAlpcConnectPort` at `0x1400012a4`
- `ntoskrnl!ZwClose` at `0x1400012ff`
- `ntoskrnl!ZwClose` at `0x1400012ff`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400011ea`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400011ea`

## pseudocode

```c
__int64 __fastcall WerpSendWersvcMessage(__int64 a1, __int64 a2)
{
  NTSTATUS started; // ebx
  int v5; // eax
  int v6; // edx
  __int64 *v7; // rdi
  int v8; // eax
  __int64 v10; // [rsp+60h] [rbp-10h] BYREF
  __int64 v11; // [rsp+68h] [rbp-8h] BYREF
  __int64 SystemInformation; // [rsp+A0h] [rbp+30h] BYREF
  HANDLE Handle; // [rsp+A8h] [rbp+38h] BYREF

  Handle = 0;
  SystemInformation = 0;
  v10 = 0;
  v11 = 0;
  started = ZwQuerySystemInformation(MaxSystemInfoClass|SystemObjectInformation, &SystemInformation, 8u, 0);
  if ( started >= 0 )
  {
    started = WerStartSystemErrorHandler();
    if ( started < 0
      || (v5 = WerWaitForSystemErrorHandler((unsigned int)SystemInformation), started = v5, v5 < 0)
      || v5 == 258 )
    {
      DbgPrintEx(
        5u,
        1u,
        "WERKERNELHOST: WerpSendWersvcMessage: WerStartSystemErrorHandler failed with NTSTATUS %08X.\n",
        (unsigned int)started);
    }
    else
    {
      if ( HIDWORD(SystemInformation) == -1 )
      {
        v6 = 1;
      }
      else
      {
        v6 = 0;
        v10 = -10000LL * SHIDWORD(SystemInformation);
      }
      v7 = &v10;
      if ( v6 )
        v7 = 0;
      v8 = ZwAlpcConnectPort(&Handle, L"BD", qword_140005948, qword_1400058F0, 0x20000, qword_140005938, 0, 0, 0, 0, v7);
      started = v8;
      if ( v8 < 0 || v8 == 258 )
      {
        DbgPrintEx(
          5u,
          1u,
          "WERKERNELHOST: WerpSendWersvcMessage: ZwAlpcConnectPort failed with NTSTATUS %08X.\n",
          (unsigned int)v8);
      }
      else
      {
        v11 = 1400;
        started = ZwAlpcSendWaitReceivePort(Handle, 0, a2, 0, a1, &v11, 0, v7);
        ZwClose(Handle);
        if ( started < 0 || started == 258 )
          DbgPrintEx(
            5u,
            1u,
            "WERKERNELHOST: WerpSendWersvcMessage: ZwAlpcSendWaitReceivePort failed with NTSTATUS %08X.\n",
            (unsigned int)started);
      }
    }
  }
  else
  {
    DbgPrintEx(
      5u,
      1u,
      "WERKERNELHOST: ZwQuerySystemInformation/SystemErrorPortTimeouts failed with NTSTATUS %08X.\n",
      (unsigned int)started);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1400011a0  mov     [rsp-18h+arg_0], rbx
0x1400011a5  mov     [rsp-18h+arg_8], rsi
0x1400011aa  push    rbp
0x1400011ab  push    rdi
0x1400011ac  push    r14
0x1400011ae  mov     rbp, rsp
0x1400011b1  sub     rsp, 70h
0x1400011b5  xor     r9d, r9d; ReturnLength
0x1400011b8  mov     [rbp+Handle], 0
0x1400011c0  mov     rsi, rdx
0x1400011c3  mov     [rbp+SystemInformation], 0
0x1400011cb  mov     r14, rcx
0x1400011ce  mov     [rbp+var_10], 0
0x1400011d6  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x1400011da  mov     [rbp+var_8], 0
0x1400011e2  lea     r8d, [r9+8]; SystemInformationLength
0x1400011e6  lea     ecx, [r9+73h]; SystemInformationClass
0x1400011ea  call    cs:__imp_ZwQuerySystemInformation
0x1400011f1  nop     dword ptr [rax+rax+00h]
0x1400011f6  mov     ebx, eax
0x1400011f8  test    eax, eax
0x1400011fa  jns     short loc_140001208
0x1400011fc  lea     r8, aWerkernelhostZ_1; "WERKERNELHOST: ZwQuerySystemInformation"...
0x140001203  jmp     loc_140001330
0x140001208  call    WerStartSystemErrorHandler
0x14000120d  mov     ebx, eax
0x14000120f  test    eax, eax
0x140001211  js      loc_140001329
0x140001217  mov     ecx, dword ptr [rbp+SystemInformation]
0x14000121a  call    WerWaitForSystemErrorHandler
0x14000121f  mov     ebx, eax
0x140001221  test    eax, eax
0x140001223  js      loc_140001329
0x140001229  cmp     eax, 102h
0x14000122e  jz      loc_140001329
0x140001234  cmp     dword ptr [rbp+SystemInformation+4], 0FFFFFFFFh
0x140001238  jnz     short loc_140001241
0x14000123a  mov     edx, 1
0x14000123f  jmp     short loc_140001252
0x140001241  movsxd  rax, dword ptr [rbp+SystemInformation+4]
0x140001245  xor     edx, edx
0x140001247  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x14000124e  mov     [rbp+var_10], rcx
0x140001252  xor     eax, eax
0x140001254  lea     rdi, [rbp+var_10]
0x140001258  test    edx, edx
0x14000125a  lea     r9, qword_1400058F0
0x140001261  lea     r8, qword_140005948
0x140001268  cmovnz  rdi, rax
0x14000126c  lea     rdx, aBd; "BD"
0x140001273  mov     [rsp+70h+var_20], rdi
0x140001278  lea     rcx, [rbp+Handle]
0x14000127c  mov     [rsp+70h+var_28], rax
0x140001281  mov     [rsp+70h+var_30], rax
0x140001286  mov     [rsp+70h+var_38], rax
0x14000128b  mov     [rsp+70h+var_40], rax
0x140001290  lea     rax, qword_140005938
0x140001297  mov     [rsp+70h+var_48], rax
0x14000129c  mov     dword ptr [rsp+70h+var_50], 20000h
0x1400012a4  call    cs:__imp_ZwAlpcConnectPort
0x1400012ab  nop     dword ptr [rax+rax+00h]
0x1400012b0  mov     ebx, eax
0x1400012b2  test    eax, eax
0x1400012b4  js      short loc_140001320
0x1400012b6  cmp     eax, 102h
0x1400012bb  jz      short loc_140001320
0x1400012bd  mov     rcx, [rbp+Handle]
0x1400012c1  lea     rax, [rbp+var_8]
0x1400012c5  mov     [rsp+70h+var_38], rdi
0x1400012ca  xor     r9d, r9d
0x1400012cd  mov     [rsp+70h+var_40], 0
0x1400012d6  mov     r8, rsi
0x1400012d9  mov     [rsp+70h+var_48], rax
0x1400012de  xor     edx, edx
0x1400012e0  mov     [rsp+70h+var_50], r14
0x1400012e5  mov     [rbp+var_8], 578h
0x1400012ed  call    cs:__imp_ZwAlpcSendWaitReceivePort
0x1400012f4  nop     dword ptr [rax+rax+00h]
0x1400012f9  mov     rcx, [rbp+Handle]; Handle
0x1400012fd  mov     ebx, eax
0x1400012ff  call    cs:__imp_ZwClose
0x140001306  nop     dword ptr [rax+rax+00h]
0x14000130b  test    ebx, ebx
0x14000130d  js      short loc_140001317
0x14000130f  cmp     ebx, 102h
0x140001315  jnz     short loc_140001347
0x140001317  lea     r8, aWerkernelhostW_35; "WERKERNELHOST: WerpSendWersvcMessage: Z"...
0x14000131e  jmp     short loc_140001330
0x140001320  lea     r8, aWerkernelhostW_51; "WERKERNELHOST: WerpSendWersvcMessage: Z"...
0x140001327  jmp     short loc_140001330
0x140001329  lea     r8, Format; "WERKERNELHOST: WerpSendWersvcMessage: W"...
0x140001330  mov     edx, 1; Level
0x140001335  mov     r9d, ebx
0x140001338  lea     ecx, [rdx+4]; ComponentId
0x14000133b  call    cs:__imp_DbgPrintEx
0x140001342  nop     dword ptr [rax+rax+00h]
0x140001347  lea     r11, [rsp+70h+var_s0]
0x14000134c  mov     eax, ebx
0x14000134e  mov     rbx, [r11+20h]
0x140001352  mov     rsi, [r11+28h]
0x140001356  mov     rsp, r11
0x140001359  pop     r14
0x14000135b  pop     rdi
0x14000135c  pop     rbp
0x14000135d  retn
```
