# SclpDisplayLegacyUi

- ea: `0x1400014c0`
- end: `0x1400015e1`
- name: `SclpDisplayLegacyUi`
- size: `289`
- prototype: `union _LARGE_INTEGER()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400014c0`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x1400014cb`
- `ntdll!NtQuerySystemTime` at `0x1400014cb`
- `ntdll!NtDisplayString` at `0x1400015a6`
- `ntdll!NtDisplayString` at `0x1400015c5`
- `ntdll!NtDisplayString` at `0x1400015a6`
- `ntdll!NtDisplayString` at `0x1400015c5`
- `ntdll!RtlInitUnicodeString` at `0x1400014ec`
- `ntdll!RtlInitUnicodeString` at `0x140001500`
- `ntdll!RtlInitUnicodeString` at `0x1400014ec`
- `ntdll!RtlInitUnicodeString` at `0x140001500`
- `setupcl!SclLoadStringResource` at `0x140001520`
- `setupcl!SclLoadStringResource` at `0x140001520`

## pseudocode

```c
union _LARGE_INTEGER SclpDisplayLegacyUi()
{
  USHORT Length; // ax
  union _LARGE_INTEGER result; // rax
  struct _UNICODE_STRING *v2; // rcx

  NtQuerySystemTime(&stru_1400035D0);
  if ( byte_140003594 )
    goto LABEL_8;
  RtlInitUnicodeString(&DisplayString, L"\r");
  RtlInitUnicodeString(&stru_1400035A8, L".");
  if ( (int)SclLoadStringResource(*(_QWORD *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 16LL), &UnicodeString, 10000) >= 0 )
  {
    Length = UnicodeString.Length;
    if ( UnicodeString.Length > 4u )
    {
      UnicodeString.Length -= 4;
      UnicodeString.Buffer[(unsigned __int64)(unsigned __int16)(Length - 4) >> 1] = 0;
    }
    byte_140003595 = 1;
  }
  if ( byte_140003594 )
  {
LABEL_8:
    result = stru_1400035D0;
    if ( stru_1400035D0.QuadPart - CurrentTime.QuadPart <= 10000000 )
      return result;
  }
  else
  {
    result = stru_1400035D0;
  }
  byte_140003594 = 1;
  CurrentTime = result;
  if ( dword_140003590 )
  {
    v2 = &stru_1400035A8;
    goto LABEL_13;
  }
  NtDisplayString(&DisplayString);
  if ( byte_140003595 )
  {
    v2 = &UnicodeString;
LABEL_13:
    NtDisplayString(v2);
  }
  result.QuadPart = ((_BYTE)dword_140003590 + 1) & 3;
  dword_140003590 = ((_BYTE)dword_140003590 + 1) & 3;
  return result;
}

```

## disassembly

```asm
0x1400014c0  sub     rsp, 28h
0x1400014c4  lea     rcx, stru_1400035D0; CurrentTime
0x1400014cb  call    cs:__imp_NtQuerySystemTime
0x1400014d1  cmp     cs:byte_140003594, 0
0x1400014d8  jnz     loc_14000156E
0x1400014de  lea     rdx, SourceString; "\r"
0x1400014e5  lea     rcx, DisplayString; DestinationString
0x1400014ec  call    cs:__imp_RtlInitUnicodeString
0x1400014f2  lea     rdx, asc_140002294; "."
0x1400014f9  lea     rcx, stru_1400035A8; DestinationString
0x140001500  call    cs:__imp_RtlInitUnicodeString
0x140001506  mov     rcx, gs:60h
0x14000150f  lea     rdx, UnicodeString
0x140001516  mov     r8d, 2710h
0x14000151c  mov     rcx, [rcx+10h]
0x140001520  call    cs:__imp_SclLoadStringResource
0x140001526  test    eax, eax
0x140001528  js      short loc_14000155C
0x14000152a  movzx   eax, cs:UnicodeString.Length
0x140001531  cmp     ax, 4
0x140001535  jbe     short loc_140001555
0x140001537  sub     ax, 4
0x14000153b  movzx   edx, ax
0x14000153e  mov     cs:UnicodeString.Length, ax
0x140001545  mov     rax, cs:UnicodeString.Buffer
0x14000154c  shr     rdx, 1
0x14000154f  xor     ecx, ecx
0x140001551  mov     [rax+rdx*2], cx
0x140001555  mov     cs:byte_140003595, 1
0x14000155c  cmp     cs:byte_140003594, 0
0x140001563  jnz     short loc_14000156E
0x140001565  mov     rax, qword ptr cs:stru_1400035D0
0x14000156c  jmp     short loc_140001588
0x14000156e  mov     rax, qword ptr cs:stru_1400035D0
0x140001575  mov     rdx, rax
0x140001578  sub     rdx, qword ptr cs:CurrentTime
0x14000157f  cmp     rdx, 989680h
0x140001586  jle     short loc_1400015DC
0x140001588  cmp     cs:dword_140003590, 0
0x14000158f  mov     cs:byte_140003594, 1
0x140001596  mov     qword ptr cs:CurrentTime, rax
0x14000159d  jnz     short loc_1400015BE
0x14000159f  lea     rcx, DisplayString; DisplayString
0x1400015a6  call    cs:__imp_NtDisplayString
0x1400015ac  cmp     cs:byte_140003595, 0
0x1400015b3  jz      short loc_1400015CB
0x1400015b5  lea     rcx, UnicodeString
0x1400015bc  jmp     short loc_1400015C5
0x1400015be  lea     rcx, stru_1400035A8; DisplayString
0x1400015c5  call    cs:__imp_NtDisplayString
0x1400015cb  mov     eax, cs:dword_140003590
0x1400015d1  inc     eax
0x1400015d3  and     eax, 3
0x1400015d6  mov     cs:dword_140003590, eax
0x1400015dc  add     rsp, 28h
0x1400015e0  retn
```
