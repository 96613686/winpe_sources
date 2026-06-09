# QueryLogCommand::PrintEvent(void *,void *)

- ea: `0x14000c928`
- end: `0x14000c981`
- name: `?PrintEvent@QueryLogCommand@@AEAAXPEAX0@Z`
- size: `89`
- prototype: `void __fastcall(QueryLogCommand *__hidden this, void *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008db0`

## callees

- `0x14000b8e8`
- `0x14000be14`
- `0x14000c928`
- `0x14000ce74`
- `0x140021b00`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall QueryLogCommand::PrintEvent(QueryLogCommand *this, void *a2, void *a3)
{
  int v3; // r9d
  int v4; // r9d
  unsigned int v5; // ebx
  HANDLE StdHandle; // rdi
  void *v7; // rax
  __int128 v8; // [rsp+20h] [rbp-68h] BYREF
  EvtException *v9; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v10[32]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v11[32]; // [rsp+58h] [rbp-30h] BYREF

  try
  {
    v3 = *((_DWORD *)this + 63);
    if ( v3 )
    {
      v4 = v3 - 1;
      if ( v4 )
      {
        if ( v4 == 1 )
          QueryLogCommand::PrintEventRenderedXml(this, a2, a3);
      }
      else
      {
        QueryLogCommand::PrintEventText(this, a2, a3);
      }
    }
    else
    {
      QueryLogCommand::PrintEventXml(this, a2);
    }
  }
  catch ( EvtException *v9 )
  {
    v5 = *((_DWORD *)v9 + 6);
    StdHandle = GetStdHandle(0xFFFFFFF4);
    *(_QWORD *)&v8 = L"Failed to render events.";
    *((_QWORD *)&v8 + 1) = 24;
    FilePuts(StdHandle, &v8);
    try
    {
      std::wstring::wstring(v10, L" Error=");
      std::to_wstring(v11, v5);
      v7 = (void *)std::wstring::_Append<wchar_t>(v10);
      std::wstring::_Append<wchar_t>(v7);
      std::wstring::_Tidy_deallocate(v11);
      v8 = *(_OWORD *)std::wstring::operator std::wstring_view(v10, v11);
      FilePuts(StdHandle, &v8);
      std::wstring::_Tidy_deallocate(v10);
    }
    catch ( ... )
    {
    }
  }
}

```

## disassembly

```asm
0x14000c928  sub     rsp, 88h
0x14000c92f  mov     rax, cs:__security_cookie
0x14000c936  xor     rax, rsp
0x14000c939  mov     [rsp+88h+var_10], rax
0x14000c93e  mov     r9d, [rcx+0FCh]
0x14000c945  test    r9d, r9d
0x14000c948  jz      short loc_14000C964
0x14000c94a  sub     r9d, 1
0x14000c94e  jz      short loc_14000C95D
0x14000c950  cmp     r9d, 1
0x14000c954  jnz     short loc_14000C96A
0x14000c956  call    ?PrintEventRenderedXml@QueryLogCommand@@AEAAXPEAX0@Z; QueryLogCommand::PrintEventRenderedXml(void *,void *)
0x14000c95b  jmp     short loc_14000C96A
0x14000c95d  call    ?PrintEventText@QueryLogCommand@@AEAAXPEAX0@Z; QueryLogCommand::PrintEventText(void *,void *)
0x14000c962  jmp     short loc_14000C95B
0x14000c964  call    ?PrintEventXml@QueryLogCommand@@AEAAXPEAX@Z; QueryLogCommand::PrintEventXml(void *)
0x14000c969  nop
0x14000c96a  jmp     short $+2
0x14000c96c  mov     rcx, [rsp+88h+var_10]
0x14000c971  xor     rcx, rsp; StackCookie
0x14000c974  call    __security_check_cookie
0x14000c979  add     rsp, 88h
0x14000c980  retn
```
