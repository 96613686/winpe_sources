# TmpReadKtmRmTmId

- ea: `0x1400018f8`
- end: `0x140001a04`
- name: `TmpReadKtmRmTmId`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140001cfc`

## callees

- `0x1400018f8`
- `0x1400024e0`
- `0x1400242b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400019da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400019da`
- `ntoskrnl!RtlGUIDFromString` at `0x1400019c2`
- `ntoskrnl!RtlGUIDFromString` at `0x1400019c2`

## string_xrefs

- `0x140001930`: `\Registry\Machine\Software\Microsoft\MSDTC\KtmRm`

## pseudocode

```c
void TmpReadKtmRmTmId()
{
  NTSTATUS v0; // eax
  PVOID v1; // rbx
  _BYTE v2[4]; // [rsp+30h] [rbp-D0h] BYREF
  ULONG v3; // [rsp+34h] [rbp-CCh] BYREF
  PVOID P; // [rsp+38h] [rbp-C8h] BYREF
  UNICODE_STRING v5; // [rsp+40h] [rbp-C0h] BYREF
  UNICODE_STRING v6; // [rsp+50h] [rbp-B0h] BYREF
  UNICODE_STRING GuidString; // [rsp+60h] [rbp-A0h] BYREF
  char v8; // [rsp+70h] [rbp-90h] BYREF

  *(_QWORD *)&v6.Length = 6422624;
  P = &v8;
  *(_QWORD *)&v5.Length = 2359330;
  v6.Buffer = L"\\Registry\\Machine\\Software\\Microsoft\\MSDTC\\KtmRm";
  v2[0] = 0;
  v5.Buffer = L"KtmRmTmIdentifier";
  v3 = 156;
  GuidString = 0;
  v0 = TmpQueryValueKey(&v6, &v5, &v3, &P, v2);
  v1 = P;
  if ( v0 >= 0 )
  {
    GuidString.Buffer = (wchar_t *)((char *)P + *((unsigned int *)P + 2));
    GuidString.Length = *((_WORD *)P + 6);
    GuidString.MaximumLength = *((_WORD *)P + 6);
    RtlGUIDFromString(&GuidString, &TmpKtmRmTmGuid);
  }
  else
  {
    TmpKtmRmTmGuid = 0;
  }
  if ( v2[0] )
    ExFreePoolWithTag(v1, 0);
}

```

## disassembly

```asm
0x1400018f8  mov     [rsp-8+arg_0], rbx
0x1400018fd  push    rbp
0x1400018fe  lea     rbp, [rsp-20h]
0x140001903  sub     rsp, 120h
0x14000190a  mov     rax, cs:__security_cookie
0x140001911  xor     rax, rsp
0x140001914  mov     [rbp+20h+var_10], rax
0x140001918  lea     rax, [rsp+120h+var_B0]
0x14000191d  mov     [rsp+120h+var_D0], 620060h
0x140001926  mov     [rsp+120h+P], rax
0x14000192b  lea     r9, [rsp+120h+P]
0x140001930  lea     rax, aRegistryMachin_0; "\\Registry\\Machine\\Software\\Microsof"...
0x140001937  mov     [rsp+120h+var_E0], 240022h
0x140001940  mov     [rsp+120h+var_C8], rax
0x140001945  lea     r8, [rsp+120h+var_EC]
0x14000194a  lea     rax, aKtmrmtmidentif; "KtmRmTmIdentifier"
0x140001951  mov     [rsp+120h+var_F0], 0
0x140001956  mov     [rsp+120h+var_D8], rax
0x14000195b  lea     rdx, [rsp+120h+var_E0]
0x140001960  lea     rax, [rsp+120h+var_F0]
0x140001965  mov     [rsp+120h+var_EC], 9Ch
0x14000196d  xorps   xmm0, xmm0
0x140001970  mov     [rsp+120h+var_100], rax
0x140001975  lea     rcx, [rsp+120h+var_D0]
0x14000197a  movups  xmmword ptr [rsp+120h+GuidString.Length], xmm0
0x14000197f  call    TmpQueryValueKey
0x140001984  mov     rbx, [rsp+120h+P]
0x140001989  test    eax, eax
0x14000198b  jns     short loc_140001999
0x14000198d  xorps   xmm0, xmm0
0x140001990  movups  xmmword ptr cs:TmpKtmRmTmGuid.Data1, xmm0
0x140001997  jmp     short loc_1400019CE
0x140001999  mov     eax, [rbx+8]
0x14000199c  lea     rdx, TmpKtmRmTmGuid; Guid
0x1400019a3  add     rax, rbx
0x1400019a6  lea     rcx, [rsp+120h+GuidString]; GuidString
0x1400019ab  mov     [rsp+120h+GuidString.Buffer], rax
0x1400019b0  movzx   eax, word ptr [rbx+0Ch]
0x1400019b4  mov     [rsp+120h+GuidString.Length], ax
0x1400019b9  movzx   eax, word ptr [rbx+0Ch]
0x1400019bd  mov     [rsp+120h+GuidString.MaximumLength], ax
0x1400019c2  call    cs:__imp_RtlGUIDFromString
0x1400019c9  nop     dword ptr [rax+rax+00h]
0x1400019ce  cmp     [rsp+120h+var_F0], 0
0x1400019d3  jz      short loc_1400019E6
0x1400019d5  xor     edx, edx; Tag
0x1400019d7  mov     rcx, rbx; P
0x1400019da  call    cs:__imp_ExFreePoolWithTag
0x1400019e1  nop     dword ptr [rax+rax+00h]
0x1400019e6  mov     rcx, [rbp+20h+var_10]
0x1400019ea  xor     rcx, rsp; StackCookie
0x1400019ed  call    __security_check_cookie
0x1400019f2  mov     rbx, [rsp+120h+arg_0]
0x1400019fa  add     rsp, 120h
0x140001a01  pop     rbp
0x140001a02  retn
```
