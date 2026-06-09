# CActivatedEventArgsBase::v_GetActivationKind(HSTRING__ *,Windows::ApplicationModel::Activation::ActivationKind *)

- ea: `0x180075d70`
- end: `0x180075e4b`
- name: `?v_GetActivationKind@CActivatedEventArgsBase@@EEAAJPEAUHSTRING__@@PEAW4ActivationKind@Activation@ApplicationModel@Windows@@@Z`
- size: `219`
- prototype: `int(CActivatedEventArgsBase *__hidden this, HSTRING, enum Windows::ApplicationModel::Activation::ActivationKind *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18007546c`
- `0x180075560`
- `0x180075d70`
- `0x180080b5c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075da3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075e36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075da3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075e36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180075d98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180075dd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180075d98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180075dd5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180075e08`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180075e08`

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
    if ( CompareStringOrdinal(StringRawBuffer, -1, (&off_18008FBF0)[2 * i], -1, 0) == 2 )
    {
      *(_DWORD *)a3 = *((_DWORD *)&off_18008FBF0 + 4 * i + 2);
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
0x180075d70  push    rbx
0x180075d72  push    rbp
0x180075d73  push    rsi
0x180075d74  push    rdi
0x180075d75  push    r12
0x180075d77  push    r14
0x180075d79  sub     rsp, 38h
0x180075d7d  mov     rdi, r8
0x180075d80  mov     rbx, rdx
0x180075d83  test    r8, r8
0x180075d86  jnz     short loc_180075D8D
0x180075d88  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pKind")
0x180075d8d  xor     edx, edx; length
0x180075d8f  mov     dword ptr [rdi], 0
0x180075d95  mov     rcx, rbx; string
0x180075d98  call    cs:__imp_WindowsGetStringRawBuffer
0x180075d9e  xor     ecx, ecx; string
0x180075da0  mov     rsi, rax
0x180075da3  call    cs:__imp_WindowsDeleteString
0x180075da9  lea     rdx, [rsp+68h+string]; HSTRING *
0x180075db1  mov     [rsp+68h+string], 0
0x180075dbd  mov     rcx, rbx; string
0x180075dc0  call    ?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z; SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)
0x180075dc5  mov     ebp, eax
0x180075dc7  test    eax, eax
0x180075dc9  js      short loc_180075DDE
0x180075dcb  mov     rcx, [rsp+68h+string]; string
0x180075dd3  xor     edx, edx; length
0x180075dd5  call    cs:__imp_WindowsGetStringRawBuffer
0x180075ddb  mov     rsi, rax
0x180075dde  xor     ebx, ebx
0x180075de0  lea     r12, off_18008FBF0; "Windows.Launch"
0x180075de7  mov     rcx, rsi; unsigned __int16 *
0x180075dea  cmp     ebx, 2Eh ; '.'
0x180075ded  jnb     short loc_180075E20
0x180075def  or      r9d, 0FFFFFFFFh; cchCount2
0x180075df3  mov     r14d, ebx
0x180075df6  add     r14, r14
0x180075df9  mov     [rsp+68h+bIgnoreCase], 0; bIgnoreCase
0x180075e01  or      edx, r9d; cchCount1
0x180075e04  mov     r8, [r12+r14*8]; lpString2
0x180075e08  call    cs:__imp_CompareStringOrdinal
0x180075e0e  cmp     eax, 2
0x180075e11  jz      short loc_180075E17
0x180075e13  inc     ebx
0x180075e15  jmp     short loc_180075DE7
0x180075e17  mov     eax, [r12+r14*8+8]
0x180075e1c  mov     [rdi], eax
0x180075e1e  jmp     short loc_180075E2E
0x180075e20  call    ?IsBackgroundExtensionContract@@YA_NPEBG@Z; IsBackgroundExtensionContract(ushort const *)
0x180075e25  test    al, al
0x180075e27  jnz     short loc_180075E2E
0x180075e29  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "fFound || IsBackgroundExtensionContract(pszContractId)")
0x180075e2e  mov     rcx, [rsp+68h+string]; string
0x180075e36  call    cs:__imp_WindowsDeleteString
0x180075e3c  mov     eax, ebp
0x180075e3e  add     rsp, 38h
0x180075e42  pop     r14
0x180075e44  pop     r12
0x180075e46  pop     rdi
0x180075e47  pop     rsi
0x180075e48  pop     rbp
0x180075e49  pop     rbx
0x180075e4a  retn
```
