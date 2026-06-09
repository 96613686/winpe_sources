# CIasMigErrorHelper::ReadStringFromResourceWithParameter(ushort const *,uint,_bstr_t &,_bstr_t &)

- ea: `0x180053e2c`
- end: `0x180053f9c`
- name: `?ReadStringFromResourceWithParameter@CIasMigErrorHelper@@SAJPEBGIAEAV_bstr_t@@1@Z`
- size: `368`
- prototype: `static int(const unsigned __int16 *, unsigned int, struct _bstr_t *, struct _bstr_t *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180054320`
- `0x1800544b0`

## callees

- `0x18002cd00`
- `0x18003f638`
- `0x180042a80`
- `0x18004724c`
- `0x180053c30`
- `0x180053e2c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180053f84`
- `KERNEL32!LocalFree` at `0x180053f84`
- `KERNEL32!GetLastError` at `0x180053f13`
- `KERNEL32!GetLastError` at `0x180053f13`
- `KERNEL32!FormatMessageW` at `0x180053f09`
- `KERNEL32!FormatMessageW` at `0x180053f09`

## string_xrefs

- `0x180053e70`: `ReadStringFromResource() failed: %!hresult!`

## pseudocode

```c
__int64 __fastcall CIasMigErrorHelper::ReadStringFromResourceWithParameter(
        const unsigned __int16 *a1,
        UINT a2,
        va_list *a3,
        struct _bstr_t *a4)
{
  unsigned int StringFromResource; // ebx
  int v7; // edx
  const char *v8; // r9
  va_list v10; // rax
  const void **v11; // rax
  const void *v12; // rdx
  signed int LastError; // eax
  WCHAR Buffer[4]; // [rsp+40h] [rbp-18h] BYREF
  va_list Arguments; // [rsp+48h] [rbp-10h] BYREF

  StringFromResource = CIasMigErrorHelper::ReadStringFromResource(a1, a2, a4);
  if ( (StringFromResource & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
    {
      return StringFromResource;
    }
    WppDbgPrint("ReadStringFromResource() failed: %!hresult!");
    v7 = 16;
    v8 = "NPSSETUP";
LABEL_6:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)WPP_a172f93e3a9532ef0a391bb7dc34d5ba_Traceguids,
      (_DWORD)v8,
      StringFromResource);
    return StringFromResource;
  }
  if ( _bstr_t::length((_bstr_t *)a3) )
  {
    v10 = *a3;
    if ( *a3 )
      v10 = *(va_list *)v10;
    Arguments = v10;
    v11 = *(const void ***)a4;
    *(_QWORD *)Buffer = 0;
    if ( v11 )
      v12 = *v11;
    else
      v12 = 0;
    if ( !FormatMessageW(0x2500u, v12, 0, 0, Buffer, 0, &Arguments) )
    {
      LastError = GetLastError();
      StringFromResource = LastError;
      if ( LastError > 0 )
        StringFromResource = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      {
        return StringFromResource;
      }
      WppDbgPrint("FormatMessageW() failed: %!hresult!");
      v7 = 17;
      v8 = "NPSDS";
      goto LABEL_6;
    }
    _bstr_t::operator=(a4, *(_QWORD *)Buffer);
    LocalFree(*(HLOCAL *)Buffer);
  }
  return 0;
}

```

## disassembly

```asm
0x180053e2c  mov     [rsp+arg_0], rbx
0x180053e31  mov     [rsp+arg_8], rsi
0x180053e36  push    rdi
0x180053e37  sub     rsp, 50h
0x180053e3b  mov     rsi, r8
0x180053e3e  mov     rdi, r9
0x180053e41  mov     r8, r9; struct _bstr_t *
0x180053e44  call    ?ReadStringFromResource@CIasMigErrorHelper@@SAJPEBGIAEAV_bstr_t@@@Z; CIasMigErrorHelper::ReadStringFromResource(ushort const *,uint,_bstr_t &)
0x180053e49  mov     ebx, eax
0x180053e4b  test    eax, eax
0x180053e4d  jns     short loc_180053EAA
0x180053e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180053e56  lea     rdx, WPP_GLOBAL_Control
0x180053e5d  cmp     rcx, rdx
0x180053e60  jz      short loc_180053EA3
0x180053e62  cmp     byte ptr [rcx+19h], 2
0x180053e66  jb      short loc_180053EA3
0x180053e68  test    byte ptr [rcx+1Ch], 40h
0x180053e6c  jz      short loc_180053EA3
0x180053e6e  mov     edx, eax
0x180053e70  lea     rcx, aReadstringfrom_0; "ReadStringFromResource() failed: %!hres"...
0x180053e77  call    WppDbgPrint
0x180053e7c  mov     edx, 10h
0x180053e81  lea     r9, aNpssetup; "NPSSETUP"
0x180053e88  mov     rcx, cs:WPP_GLOBAL_Control
0x180053e8f  lea     r8, WPP_a172f93e3a9532ef0a391bb7dc34d5ba_Traceguids
0x180053e96  mov     dword ptr [rsp+58h+lpBuffer], ebx
0x180053e9a  mov     rcx, [rcx+10h]
0x180053e9e  call    WPP_SF_sd
0x180053ea3  mov     eax, ebx
0x180053ea5  jmp     loc_180053F8C
0x180053eaa  mov     rcx, rsi; this
0x180053ead  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180053eb2  test    eax, eax
0x180053eb4  jz      loc_180053F8A
0x180053eba  mov     rax, [rsi]
0x180053ebd  test    rax, rax
0x180053ec0  jz      short loc_180053EC5
0x180053ec2  mov     rax, [rax]
0x180053ec5  mov     [rsp+58h+var_10], rax
0x180053eca  mov     rax, [rdi]
0x180053ecd  mov     qword ptr [rsp+58h+Buffer], 0
0x180053ed6  test    rax, rax
0x180053ed9  jz      short loc_180053EE0
0x180053edb  mov     rdx, [rax]
0x180053ede  jmp     short loc_180053EE2
0x180053ee0  xor     edx, edx; lpSource
0x180053ee2  lea     rax, [rsp+58h+var_10]
0x180053ee7  xor     r9d, r9d; dwLanguageId
0x180053eea  mov     [rsp+58h+Arguments], rax; Arguments
0x180053eef  xor     r8d, r8d; dwMessageId
0x180053ef2  lea     rax, [rsp+58h+Buffer]
0x180053ef7  mov     [rsp+58h+nSize], 0; nSize
0x180053eff  mov     ecx, 2500h; dwFlags
0x180053f04  mov     [rsp+58h+lpBuffer], rax; lpBuffer
0x180053f09  call    cs:__imp_FormatMessageW
0x180053f0f  test    eax, eax
0x180053f11  jnz     short loc_180053F72
0x180053f13  call    cs:__imp_GetLastError
0x180053f19  mov     ebx, eax
0x180053f1b  test    eax, eax
0x180053f1d  jle     short loc_180053F28
0x180053f1f  movzx   ebx, ax
0x180053f22  or      ebx, 80070000h
0x180053f28  mov     rax, cs:WPP_GLOBAL_Control
0x180053f2f  lea     rdx, WPP_GLOBAL_Control
0x180053f36  cmp     rax, rdx
0x180053f39  jz      loc_180053EA3
0x180053f3f  cmp     byte ptr [rax+19h], 2
0x180053f43  jb      loc_180053EA3
0x180053f49  test    byte ptr [rax+1Ch], 10h
0x180053f4d  jz      loc_180053EA3
0x180053f53  mov     edx, ebx
0x180053f55  lea     rcx, aFormatmessagew; "FormatMessageW() failed: %!hresult!"
0x180053f5c  call    WppDbgPrint
0x180053f61  mov     edx, 11h
0x180053f66  lea     r9, aNpsds; "NPSDS"
0x180053f6d  jmp     loc_180053E88
0x180053f72  mov     rdx, qword ptr [rsp+58h+Buffer]
0x180053f77  mov     rcx, rdi
0x180053f7a  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180053f7f  mov     rcx, qword ptr [rsp+58h+Buffer]; hMem
0x180053f84  call    cs:__imp_LocalFree
0x180053f8a  xor     eax, eax
0x180053f8c  mov     rbx, [rsp+58h+arg_0]
0x180053f91  mov     rsi, [rsp+58h+arg_8]
0x180053f96  add     rsp, 50h
0x180053f9a  pop     rdi
0x180053f9b  retn
```
