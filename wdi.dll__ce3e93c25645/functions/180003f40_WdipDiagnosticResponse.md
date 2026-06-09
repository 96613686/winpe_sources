# WdipDiagnosticResponse

- ea: `0x180003f40`
- end: `0x1800040f8`
- name: `WdipDiagnosticResponse`
- size: `440`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800063d0`

## callees

- `0x180002ba0`
- `0x180003f40`
- `0x180007d40`

## import_xrefs

- `ntdll!NtAlpcSendWaitReceivePort` at `0x180003ff6`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000409b`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180003ff6`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000409b`
- `ntdll!RtlNtStatusToDosError` at `0x180004007`
- `ntdll!RtlNtStatusToDosError` at `0x1800040ac`
- `ntdll!RtlNtStatusToDosError` at `0x180004007`
- `ntdll!RtlNtStatusToDosError` at `0x1800040ac`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x180003f86`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x180003f86`

## string_xrefs

- `0x18000403f`: `clientcore\base\diagnosis\pdi\wdi\framework\library\communicationcli.cpp`
- `0x180004063`: `clientcore\base\diagnosis\pdi\wdi\framework\library\communicationcli.cpp`
- `0x1800040dd`: `clientcore\base\diagnosis\pdi\wdi\framework\library\communicationcli.cpp`

## pseudocode

```c
__int64 __fastcall WdipDiagnosticResponse(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  int Args; // eax
  signed int v8; // edi
  __int64 v9; // rcx
  NTSTATUS v10; // eax
  signed int v11; // eax
  __int64 v12; // rcx
  NTSTATUS v13; // eax
  signed int v14; // eax
  bool v15; // sf

  LOWORD(v3) = 248;
  if ( *(_DWORD *)(a3 + 44) == 3 )
    *(_DWORD *)(a3 + 44) = 2;
  if ( *(int *)(a3 + 112) >= 0 )
  {
    v3 = *(_DWORD *)(a3 + 124) + 48 + **(_DWORD **)(a2 + 32);
    if ( v3 > (unsigned __int64)AlpcMaxAllowedMessageLength() || v3 < 0xF8 )
    {
      v8 = -2147024774;
      goto LABEL_15;
    }
    Args = WdipWriteParameterCollectionToMessageBuffer(*(_QWORD *)(a2 + 32), a3, v3);
    v8 = Args;
    if ( Args < 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\communicationcli.cpp",
        (int)L"WdipDiagnosticResponse",
        328,
        (int)L"Error = %d",
        Args);
      goto LABEL_15;
    }
  }
  v9 = *(_QWORD *)(a1 + 56);
  *(_WORD *)a3 = v3 - 40;
  *(_WORD *)(a3 + 2) = v3;
  v10 = NtAlpcSendWaitReceivePort(v9, 0x10000, a3, 0, 0, 0, 0, 0);
  if ( v10 < 0 )
  {
    v11 = RtlNtStatusToDosError(v10);
    v8 = v11;
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
  }
  else
  {
    v8 = 0;
  }
  if ( v8 < 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\communicationcli.cpp",
      (int)L"WdipSendASyncMessage",
      264,
      (int)L"Error = %d",
      v8);
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\communicationcli.cpp",
      (int)L"WdipDiagnosticResponse",
      337,
      (int)L"Error = %d",
      v8);
LABEL_15:
    *(_DWORD *)(a3 + 112) = v8;
    v12 = *(_QWORD *)(a1 + 56);
    *(_DWORD *)a3 = 16253136;
    v13 = NtAlpcSendWaitReceivePort(v12, 0x10000, a3, 0, 0, 0, 0, 0);
    if ( v13 < 0 )
    {
      v14 = RtlNtStatusToDosError(v13);
      v15 = v14 < 0;
      if ( v14 <= 0 )
        goto LABEL_20;
      v14 = (unsigned __int16)v14 | 0x80070000;
    }
    else
    {
      v14 = 0;
    }
    v15 = v14 < 0;
LABEL_20:
    if ( v15 )
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\communicationcli.cpp",
        (int)L"WdipSendASyncMessage",
        264,
        (int)L"Error = %d",
        v14);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003f40  push    rbx
0x180003f42  push    rbp
0x180003f43  push    rsi
0x180003f44  push    rdi
0x180003f45  push    r14
0x180003f47  push    r15
0x180003f49  sub     rsp, 48h
0x180003f4d  cmp     dword ptr [r8+2Ch], 3
0x180003f52  mov     r15d, 0F8h
0x180003f58  mov     ebx, r15d
0x180003f5b  mov     rsi, r8
0x180003f5e  mov     rdi, rdx
0x180003f61  mov     rbp, rcx
0x180003f64  jnz     short loc_180003F6E
0x180003f66  mov     dword ptr [r8+2Ch], 2
0x180003f6e  xor     r14d, r14d
0x180003f71  cmp     [r8+70h], r14d
0x180003f75  jl      short loc_180003FC9
0x180003f77  mov     rax, [rdx+20h]
0x180003f7b  mov     ecx, [r8+7Ch]
0x180003f7f  add     ecx, 30h ; '0'
0x180003f82  mov     ebx, [rax]
0x180003f84  add     ebx, ecx
0x180003f86  call    cs:__imp_AlpcMaxAllowedMessageLength
0x180003f8c  mov     ecx, ebx
0x180003f8e  cmp     rcx, rax
0x180003f91  ja      short loc_180003FBF
0x180003f93  cmp     ebx, r15d
0x180003f96  jb      short loc_180003FBF
0x180003f98  mov     rcx, [rdi+20h]
0x180003f9c  mov     r8d, ebx
0x180003f9f  mov     rdx, rsi
0x180003fa2  call    WdipWriteParameterCollectionToMessageBuffer
0x180003fa7  mov     edi, eax
0x180003fa9  test    eax, eax
0x180003fab  jns     short loc_180003FC9
0x180003fad  movzx   eax, ax
0x180003fb0  mov     r8d, 148h
0x180003fb6  mov     dword ptr [rsp+78h+Args], eax
0x180003fba  jmp     loc_180004055
0x180003fbf  mov     edi, 8007007Ah
0x180003fc4  jmp     loc_18000406F
0x180003fc9  mov     rcx, [rbp+38h]
0x180003fcd  lea     eax, [rbx-28h]
0x180003fd0  mov     [rsp+78h+var_40], r14
0x180003fd5  xor     r9d, r9d
0x180003fd8  mov     [rsp+78h+var_48], r14
0x180003fdd  mov     r8, rsi
0x180003fe0  mov     [rsp+78h+var_50], r14
0x180003fe5  mov     edx, 10000h
0x180003fea  mov     qword ptr [rsp+78h+Args], r14
0x180003fef  mov     [rsi], ax
0x180003ff2  mov     [rsi+2], bx
0x180003ff6  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180003ffc  test    eax, eax
0x180003ffe  js      short loc_180004005
0x180004000  mov     edi, r14d
0x180004003  jmp     short loc_18000401C
0x180004005  mov     ecx, eax; Status
0x180004007  call    cs:__imp_RtlNtStatusToDosError
0x18000400d  mov     edi, eax
0x18000400f  test    eax, eax
0x180004011  jle     short loc_18000401C
0x180004013  movzx   edi, ax
0x180004016  or      edi, 80070000h
0x18000401c  test    edi, edi
0x18000401e  jns     loc_1800040E9
0x180004024  movzx   ebx, di
0x180004027  lea     r9, aErrorD_0; "Error = %d"
0x18000402e  mov     r8d, 108h; int
0x180004034  mov     dword ptr [rsp+78h+Args], ebx; Args
0x180004038  lea     rdx, aWdipsendasyncm; "WdipSendASyncMessage"
0x18000403f  lea     rcx, aClientcoreBase; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180004046  call    WdipTraceError
0x18000404b  mov     r8d, 151h; int
0x180004051  mov     dword ptr [rsp+78h+Args], ebx; Args
0x180004055  lea     r9, aErrorD_0; "Error = %d"
0x18000405c  lea     rdx, aWdipdiagnostic; "WdipDiagnosticResponse"
0x180004063  lea     rcx, aClientcoreBase; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000406a  call    WdipTraceError
0x18000406f  mov     [rsp+78h+var_40], r14
0x180004074  xor     r9d, r9d
0x180004077  mov     [rsp+78h+var_48], r14
0x18000407c  mov     r8, rsi
0x18000407f  mov     [rsi+70h], edi
0x180004082  mov     edx, 10000h
0x180004087  mov     rcx, [rbp+38h]
0x18000408b  mov     [rsp+78h+var_50], r14
0x180004090  mov     qword ptr [rsp+78h+Args], r14
0x180004095  mov     dword ptr [rsi], 0F800D0h
0x18000409b  call    cs:__imp_NtAlpcSendWaitReceivePort
0x1800040a1  test    eax, eax
0x1800040a3  js      short loc_1800040AA
0x1800040a5  mov     eax, r14d
0x1800040a8  jmp     short loc_1800040BE
0x1800040aa  mov     ecx, eax; Status
0x1800040ac  call    cs:__imp_RtlNtStatusToDosError
0x1800040b2  test    eax, eax
0x1800040b4  jle     short loc_1800040C0
0x1800040b6  movzx   eax, ax
0x1800040b9  or      eax, 80070000h
0x1800040be  test    eax, eax
0x1800040c0  jns     short loc_1800040E9
0x1800040c2  movzx   eax, ax
0x1800040c5  lea     r9, aErrorD_0; "Error = %d"
0x1800040cc  mov     r8d, 108h; int
0x1800040d2  mov     dword ptr [rsp+78h+Args], eax; Args
0x1800040d6  lea     rdx, aWdipsendasyncm; "WdipSendASyncMessage"
0x1800040dd  lea     rcx, aClientcoreBase; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800040e4  call    WdipTraceError
0x1800040e9  mov     eax, edi
0x1800040eb  add     rsp, 48h
0x1800040ef  pop     r15
0x1800040f1  pop     r14
0x1800040f3  pop     rdi
0x1800040f4  pop     rsi
0x1800040f5  pop     rbp
0x1800040f6  pop     rbx
0x1800040f7  retn
```
