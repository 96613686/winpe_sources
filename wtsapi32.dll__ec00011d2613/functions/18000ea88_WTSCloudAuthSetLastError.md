# _WTSCloudAuthSetLastError

- ea: `0x18000ea88`
- end: `0x18000eb12`
- name: `_WTSCloudAuthSetLastError`
- size: `138`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ecb0`
- `0x18000ed20`
- `0x18000eda0`
- `0x18000edf0`
- `0x18000ee50`

## callees

- `0x180001008`
- `0x18000ea88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb0b`

## pseudocode

```c
void __fastcall WTSCloudAuthSetLastError(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // ebx
  int v5; // [rsp+40h] [rbp+8h] BYREF
  const char *v6; // [rsp+48h] [rbp+10h] BYREF

  v4 = a1;
  if ( (int)a1 < 0 )
  {
    if ( (a1 & 0x1FFF0000) == 0x70000 )
    {
      LODWORD(a1) = (unsigned __int16)a1;
    }
    else
    {
      if ( (_DWORD)a1 == -2147467261 )
      {
        v4 = 87;
      }
      else if ( (_DWORD)a1 == -2147418113 )
      {
        v4 = 1359;
      }
      else if ( (unsigned int)dword_18001F000 > 4 )
      {
        v5 = a1;
        v6 = "We did not translate an error code from HRESULT to Win32 error code.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          a1,
          (unsigned __int8 *)byte_180019F29,
          a3,
          a4,
          (const unsigned __int16 **)&v6,
          (__int64)&v5);
      }
      LODWORD(a1) = v4;
    }
    SetLastError(a1);
  }
  else
  {
    SetLastError(0);
  }
}

```

## disassembly

```asm
0x18000ea88  push    rbx
0x18000ea8a  sub     rsp, 30h
0x18000ea8e  mov     ebx, ecx
0x18000ea90  test    ecx, ecx
0x18000ea92  js      short loc_18000EA98
0x18000ea94  xor     ecx, ecx
0x18000ea96  jmp     short loc_18000EB06
0x18000ea98  mov     eax, ecx
0x18000ea9a  and     eax, 1FFF0000h
0x18000ea9f  cmp     eax, 70000h
0x18000eaa4  jnz     short loc_18000EAAB
0x18000eaa6  movzx   ecx, cx
0x18000eaa9  jmp     short loc_18000EB06
0x18000eaab  cmp     ecx, 80004003h
0x18000eab1  jz      short loc_18000EAFF
0x18000eab3  cmp     ecx, 8000FFFFh
0x18000eab9  jz      short loc_18000EAF8
0x18000eabb  mov     eax, cs:dword_18001F000
0x18000eac1  cmp     eax, 4
0x18000eac4  jbe     short loc_18000EB04
0x18000eac6  lea     rax, aWeDidNotTransl; "We did not translate an error code from"...
0x18000eacd  mov     [rsp+38h+arg_0], ecx
0x18000ead1  mov     [rsp+38h+arg_8], rax
0x18000ead6  lea     rdx, byte_180019F29
0x18000eadd  lea     rax, [rsp+38h+arg_0]
0x18000eae2  mov     [rsp+38h+var_10], rax
0x18000eae7  lea     rax, [rsp+38h+arg_8]
0x18000eaec  mov     [rsp+38h+var_18], rax
0x18000eaf1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000eaf6  jmp     short loc_18000EB04
0x18000eaf8  mov     ebx, 54Fh
0x18000eafd  jmp     short loc_18000EB04
0x18000eaff  mov     ebx, 57h ; 'W'
0x18000eb04  mov     ecx, ebx
0x18000eb06  add     rsp, 30h
0x18000eb0a  pop     rbx
0x18000eb0b  jmp     cs:__imp_SetLastError
```
