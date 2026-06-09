# CActivatedEventArgsBase::v_GetActivationKind(HSTRING__ *,Windows::ApplicationModel::Activation::ActivationKind *)

- ea: `0x1800c7070`
- end: `0x1800c714b`
- name: `?v_GetActivationKind@CActivatedEventArgsBase@@EEAAJPEAUHSTRING__@@PEAW4ActivationKind@Activation@ApplicationModel@Windows@@@Z`
- size: `219`
- prototype: `int(CActivatedEventArgsBase *__hidden this, HSTRING, enum Windows::ApplicationModel::Activation::ActivationKind *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800c6658`
- `0x1800c674c`
- `0x1800c7070`
- `0x1800c7154`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c7108`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c7108`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c7098`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c70d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c7098`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c70d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c70a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7136`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c70a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7136`

## pseudocode

```c
__int64 __fastcall CActivatedEventArgsBase::v_GetActivationKind(
        CActivatedEventArgsBase *this,
        HSTRING a2,
        enum Windows::ApplicationModel::Activation::ActivationKind *a3)
{
  WCHAR *StringRawBuffer; // rsi
  HSTRING *v6; // r8
  int v7; // ebp
  unsigned int i; // ebx
  __int64 v9; // rcx
  HSTRING string; // [rsp+80h] [rbp+18h] BYREF

  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  *(_DWORD *)a3 = 0;
  StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(a2, 0);
  WindowsDeleteString(0);
  string = 0;
  v7 = SplitActionAndServiceId(a2, &string, v6);
  if ( v7 >= 0 )
    StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
  for ( i = 0; i < 0x2E; ++i )
  {
    if ( CompareStringOrdinal(StringRawBuffer, -1, (&off_180100BD0)[2 * i], -1, 0) == 2 )
    {
      *(_DWORD *)a3 = *((_DWORD *)&off_180100BD0 + 4 * i + 2);
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
0x1800c7070  push    rbx
0x1800c7072  push    rbp
0x1800c7073  push    rsi
0x1800c7074  push    rdi
0x1800c7075  push    r12
0x1800c7077  push    r14
0x1800c7079  sub     rsp, 38h
0x1800c707d  mov     rdi, r8
0x1800c7080  mov     rbx, rdx
0x1800c7083  test    r8, r8
0x1800c7086  jnz     short loc_1800C708D
0x1800c7088  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800c708d  xor     edx, edx; length
0x1800c708f  mov     dword ptr [rdi], 0
0x1800c7095  mov     rcx, rbx; string
0x1800c7098  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c709e  xor     ecx, ecx; string
0x1800c70a0  mov     rsi, rax
0x1800c70a3  call    cs:__imp_WindowsDeleteString
0x1800c70a9  lea     rdx, [rsp+68h+string]; HSTRING *
0x1800c70b1  mov     [rsp+68h+string], 0
0x1800c70bd  mov     rcx, rbx; string
0x1800c70c0  call    ?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z; SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)
0x1800c70c5  mov     ebp, eax
0x1800c70c7  test    eax, eax
0x1800c70c9  js      short loc_1800C70DE
0x1800c70cb  mov     rcx, [rsp+68h+string]; string
0x1800c70d3  xor     edx, edx; length
0x1800c70d5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c70db  mov     rsi, rax
0x1800c70de  xor     ebx, ebx
0x1800c70e0  lea     r12, off_180100BD0; "Windows.Launch"
0x1800c70e7  mov     rcx, rsi; String1
0x1800c70ea  cmp     ebx, 2Eh ; '.'
0x1800c70ed  jnb     short loc_1800C7120
0x1800c70ef  or      r9d, 0FFFFFFFFh; cchCount2
0x1800c70f3  mov     r14d, ebx
0x1800c70f6  add     r14, r14
0x1800c70f9  mov     [rsp+68h+bIgnoreCase], 0; bIgnoreCase
0x1800c7101  or      edx, r9d; cchCount1
0x1800c7104  mov     r8, [r12+r14*8]; lpString2
0x1800c7108  call    cs:__imp_CompareStringOrdinal
0x1800c710e  cmp     eax, 2
0x1800c7111  jz      short loc_1800C7117
0x1800c7113  inc     ebx
0x1800c7115  jmp     short loc_1800C70E7
0x1800c7117  mov     eax, [r12+r14*8+8]
0x1800c711c  mov     [rdi], eax
0x1800c711e  jmp     short loc_1800C712E
0x1800c7120  call    ?IsBackgroundExtensionContract@@YA_NPEBG@Z; IsBackgroundExtensionContract(ushort const *)
0x1800c7125  test    al, al
0x1800c7127  jnz     short loc_1800C712E
0x1800c7129  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800c712e  mov     rcx, [rsp+68h+string]; string
0x1800c7136  call    cs:__imp_WindowsDeleteString
0x1800c713c  mov     eax, ebp
0x1800c713e  add     rsp, 38h
0x1800c7142  pop     r14
0x1800c7144  pop     r12
0x1800c7146  pop     rdi
0x1800c7147  pop     rsi
0x1800c7148  pop     rbp
0x1800c7149  pop     rbx
0x1800c714a  retn
```
