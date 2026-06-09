# TaskXmlReader::LoadValue(_GUID &)

- ea: `0x18001def0`
- end: `0x18001dfaf`
- name: `?LoadValue@TaskXmlReader@@AEAAJAEAU_GUID@@@Z`
- size: `191`
- prototype: `int(TaskXmlReader *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001f380`

## callees

- `0x180005f7c`
- `0x18000a8ec`
- `0x18001d7dc`
- `0x18001def0`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001df32`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001df7b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001df32`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001df7b`

## pseudocode

```c
__int64 __fastcall TaskXmlReader::LoadValue(TaskXmlReader *this, struct _GUID *a2)
{
  XmlParserTempString *v2; // rdi
  __int64 result; // rax
  const OLECHAR *NullTerminated; // rax
  HRESULT v6; // ebx
  BSTR v7; // rax
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
0x18001def0  mov     [rsp+arg_10], rbx
0x18001def5  mov     [rsp+arg_18], rsi
0x18001defa  push    rdi
0x18001defb  sub     rsp, 80h
0x18001df02  mov     rax, cs:__security_cookie
0x18001df09  xor     rax, rsp
0x18001df0c  mov     [rsp+88h+var_18], rax
0x18001df11  lea     rdi, [rcx+40h]
0x18001df15  mov     rsi, rdx
0x18001df18  mov     rdx, rdi; struct XmlParserTempString *
0x18001df1b  call    ?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z; TaskXmlReader::LoadRawValue(XmlParserTempString &)
0x18001df20  test    eax, eax
0x18001df22  js      short loc_18001DF8D
0x18001df24  mov     rcx, rdi; this
0x18001df27  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18001df2c  mov     rcx, rax; lpsz
0x18001df2f  mov     rdx, rsi; pclsid
0x18001df32  call    cs:__imp_CLSIDFromString
0x18001df38  mov     ebx, eax
0x18001df3a  test    eax, eax
0x18001df3c  jns     short loc_18001DF8B
0x18001df3e  mov     rcx, rdi; this
0x18001df41  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18001df46  cmp     word ptr [rax], 7Bh ; '{'
0x18001df4a  jz      short loc_18001DF87
0x18001df4c  mov     rcx, rdi; this
0x18001df4f  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18001df54  mov     r9, rax
0x18001df57  lea     r8, aS_0; "{%s}"
0x18001df5e  mov     edx, 28h ; '('; unsigned __int64
0x18001df63  lea     rcx, [rsp+88h+sz]; unsigned __int16 *
0x18001df68  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001df6d  mov     ebx, eax
0x18001df6f  test    eax, eax
0x18001df71  js      short loc_18001DF87
0x18001df73  mov     rdx, rsi; pclsid
0x18001df76  lea     rcx, [rsp+88h+sz]; lpsz
0x18001df7b  call    cs:__imp_CLSIDFromString
0x18001df81  mov     ebx, eax
0x18001df83  test    eax, eax
0x18001df85  jns     short loc_18001DF8B
0x18001df87  mov     eax, ebx
0x18001df89  jmp     short loc_18001DF8D
0x18001df8b  xor     eax, eax
0x18001df8d  mov     rcx, [rsp+88h+var_18]
0x18001df92  xor     rcx, rsp; StackCookie
0x18001df95  call    __security_check_cookie
0x18001df9a  lea     r11, [rsp+88h+var_8]
0x18001dfa2  mov     rbx, [r11+20h]
0x18001dfa6  mov     rsi, [r11+28h]
0x18001dfaa  mov     rsp, r11
0x18001dfad  pop     rdi
0x18001dfae  retn
```
