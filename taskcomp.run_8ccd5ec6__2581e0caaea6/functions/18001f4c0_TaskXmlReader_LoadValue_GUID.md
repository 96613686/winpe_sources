# TaskXmlReader::LoadValue(_GUID &)

- ea: `0x18001f4c0`
- end: `0x18001f58c`
- name: `?LoadValue@TaskXmlReader@@AEAAJAEAU_GUID@@@Z`
- size: `204`
- prototype: `int(TaskXmlReader *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002096c`

## callees

- `0x180006314`
- `0x18000aedc`
- `0x18001ed88`
- `0x18001f4c0`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001f502`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001f551`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001f502`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001f551`

## pseudocode

```c
__int64 __fastcall TaskXmlReader::LoadValue(TaskXmlReader *this, struct _GUID *a2)
{
  XmlParserTempString *v2; // rdi
  __int64 result; // rax
  const OLECHAR *NullTerminated; // rax
  HRESULT v6; // ebx
  unsigned __int16 *v7; // rax
  OLECHAR sz[40]; // [rsp+20h] [rbp-68h] BYREF

  v2 = (TaskXmlReader *)((char *)this + 64);
  result = TaskXmlReader::LoadRawValue(this, (TaskXmlReader *)((char *)this + 64));
  if ( (int)result >= 0 )
  {
    NullTerminated = XmlParserTempString::GetNullTerminated(v2);
    v6 = CLSIDFromString(NullTerminated, a2);
    if ( v6 < 0
      && (*XmlParserTempString::GetNullTerminated(v2) == 123
       || (v7 = XmlParserTempString::GetNullTerminated(v2), v6 = StringCchPrintfW(sz, 0x28u, L"{%s}", v7), v6 < 0)
       || (v6 = CLSIDFromString(sz, a2), v6 < 0)) )
    {
      return (unsigned int)v6;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001f4c0  mov     [rsp+arg_10], rbx
0x18001f4c5  mov     [rsp+arg_18], rsi
0x18001f4ca  push    rdi
0x18001f4cb  sub     rsp, 80h
0x18001f4d2  mov     rax, cs:__security_cookie
0x18001f4d9  xor     rax, rsp
0x18001f4dc  mov     [rsp+88h+var_18], rax
0x18001f4e1  lea     rdi, [rcx+40h]
0x18001f4e5  mov     rsi, rdx
0x18001f4e8  mov     rdx, rdi; struct XmlParserTempString *
0x18001f4eb  call    ?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z; TaskXmlReader::LoadRawValue(XmlParserTempString &)
0x18001f4f0  test    eax, eax
0x18001f4f2  js      short loc_18001F569
0x18001f4f4  mov     rcx, rdi; this
0x18001f4f7  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18001f4fc  mov     rcx, rax; lpsz
0x18001f4ff  mov     rdx, rsi; pclsid
0x18001f502  call    cs:__imp_CLSIDFromString
0x18001f509  nop     dword ptr [rax+rax+00h]
0x18001f50e  mov     ebx, eax
0x18001f510  test    eax, eax
0x18001f512  jns     short loc_18001F567
0x18001f514  mov     rcx, rdi; this
0x18001f517  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18001f51c  cmp     word ptr [rax], 7Bh ; '{'
0x18001f520  jz      short loc_18001F563
0x18001f522  mov     rcx, rdi; this
0x18001f525  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18001f52a  mov     r9, rax
0x18001f52d  lea     r8, aS_0; "{%s}"
0x18001f534  mov     edx, 28h ; '('; unsigned __int64
0x18001f539  lea     rcx, [rsp+88h+sz]; unsigned __int16 *
0x18001f53e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f543  mov     ebx, eax
0x18001f545  test    eax, eax
0x18001f547  js      short loc_18001F563
0x18001f549  mov     rdx, rsi; pclsid
0x18001f54c  lea     rcx, [rsp+88h+sz]; lpsz
0x18001f551  call    cs:__imp_CLSIDFromString
0x18001f558  nop     dword ptr [rax+rax+00h]
0x18001f55d  mov     ebx, eax
0x18001f55f  test    eax, eax
0x18001f561  jns     short loc_18001F567
0x18001f563  mov     eax, ebx
0x18001f565  jmp     short loc_18001F569
0x18001f567  xor     eax, eax
0x18001f569  mov     rcx, [rsp+88h+var_18]
0x18001f56e  xor     rcx, rsp; StackCookie
0x18001f571  call    __security_check_cookie
0x18001f576  lea     r11, [rsp+88h+var_8]
0x18001f57e  mov     rbx, [r11+20h]
0x18001f582  mov     rsi, [r11+28h]
0x18001f586  mov     rsp, r11
0x18001f589  pop     rdi
0x18001f58a  retn
```
