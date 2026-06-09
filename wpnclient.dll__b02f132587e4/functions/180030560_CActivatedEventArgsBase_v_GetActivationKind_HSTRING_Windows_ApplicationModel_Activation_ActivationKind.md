# CActivatedEventArgsBase::v_GetActivationKind(HSTRING__ *,Windows::ApplicationModel::Activation::ActivationKind *)

- ea: `0x180030560`
- end: `0x18003063b`
- name: `?v_GetActivationKind@CActivatedEventArgsBase@@EEAAJPEAUHSTRING__@@PEAW4ActivationKind@Activation@ApplicationModel@Windows@@@Z`
- size: `219`
- prototype: `int(CActivatedEventArgsBase *__hidden this, HSTRING, enum Windows::ApplicationModel::Activation::ActivationKind *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18002eb68`
- `0x18002fc28`
- `0x180030560`
- `0x180030644`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800305f8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800305f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800305c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800305c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030593`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030626`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030593`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030626`

## pseudocode

```c
__int64 __fastcall CActivatedEventArgsBase::v_GetActivationKind(
        CActivatedEventArgsBase *this,
        HSTRING a2,
        enum Windows::ApplicationModel::Activation::ActivationKind *a3)
{
  const WCHAR *StringRawBuffer; // rsi
  HSTRING *v6; // r8
  int v7; // ebp
  unsigned int i; // ebx
  __int64 v9; // rcx
  HSTRING string; // [rsp+80h] [rbp+18h] BYREF

  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  *(_DWORD *)a3 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  WindowsDeleteString(0);
  string = 0;
  v7 = SplitActionAndServiceId(a2, &string, v6);
  if ( v7 >= 0 )
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  for ( i = 0; i < 0x2E; ++i )
  {
    if ( CompareStringOrdinal(StringRawBuffer, -1, (&off_180036790)[2 * i], -1, 0) == 2 )
    {
      *(_DWORD *)a3 = *((_DWORD *)&off_180036790 + 4 * i + 2);
      goto LABEL_12;
    }
  }
  if ( !IsBackgroundExtensionContract(StringRawBuffer) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9);
LABEL_12:
  WindowsDeleteString(string);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180030560  push    rbx
0x180030562  push    rbp
0x180030563  push    rsi
0x180030564  push    rdi
0x180030565  push    r12
0x180030567  push    r14
0x180030569  sub     rsp, 38h
0x18003056d  mov     rdi, r8
0x180030570  mov     rbx, rdx
0x180030573  test    r8, r8
0x180030576  jnz     short loc_18003057D
0x180030578  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003057d  xor     edx, edx; length
0x18003057f  mov     dword ptr [rdi], 0
0x180030585  mov     rcx, rbx; string
0x180030588  call    cs:__imp_WindowsGetStringRawBuffer
0x18003058e  xor     ecx, ecx; string
0x180030590  mov     rsi, rax
0x180030593  call    cs:__imp_WindowsDeleteString
0x180030599  lea     rdx, [rsp+68h+string]; HSTRING *
0x1800305a1  mov     [rsp+68h+string], 0
0x1800305ad  mov     rcx, rbx; string
0x1800305b0  call    ?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z; SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)
0x1800305b5  mov     ebp, eax
0x1800305b7  test    eax, eax
0x1800305b9  js      short loc_1800305CE
0x1800305bb  mov     rcx, [rsp+68h+string]; string
0x1800305c3  xor     edx, edx; length
0x1800305c5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800305cb  mov     rsi, rax
0x1800305ce  xor     ebx, ebx
0x1800305d0  lea     r12, off_180036790; "Windows.Launch"
0x1800305d7  mov     rcx, rsi; unsigned __int16 *
0x1800305da  cmp     ebx, 2Eh ; '.'
0x1800305dd  jnb     short loc_180030610
0x1800305df  or      r9d, 0FFFFFFFFh; cchCount2
0x1800305e3  mov     r14d, ebx
0x1800305e6  add     r14, r14
0x1800305e9  mov     [rsp+68h+bIgnoreCase], 0; bIgnoreCase
0x1800305f1  or      edx, r9d; cchCount1
0x1800305f4  mov     r8, [r12+r14*8]; lpString2
0x1800305f8  call    cs:__imp_CompareStringOrdinal
0x1800305fe  cmp     eax, 2
0x180030601  jz      short loc_180030607
0x180030603  inc     ebx
0x180030605  jmp     short loc_1800305D7
0x180030607  mov     eax, [r12+r14*8+8]
0x18003060c  mov     [rdi], eax
0x18003060e  jmp     short loc_18003061E
0x180030610  call    ?IsBackgroundExtensionContract@@YA_NPEBG@Z; IsBackgroundExtensionContract(ushort const *)
0x180030615  test    al, al
0x180030617  jnz     short loc_18003061E
0x180030619  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003061e  mov     rcx, [rsp+68h+string]; string
0x180030626  call    cs:__imp_WindowsDeleteString
0x18003062c  mov     eax, ebp
0x18003062e  add     rsp, 38h
0x180030632  pop     r14
0x180030634  pop     r12
0x180030636  pop     rdi
0x180030637  pop     rsi
0x180030638  pop     rbp
0x180030639  pop     rbx
0x18003063a  retn
```
