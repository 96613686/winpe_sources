# TranslateRpcServiceError(long,char const *)

- ea: `0x18000dd84`
- end: `0x18000de36`
- name: `?TranslateRpcServiceError@@YAJJPEBD@Z`
- size: `178`
- prototype: `__int64 __fastcall(unsigned int, const char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000de3c`

## callees

- `0x18000c618`
- `0x18000cec8`
- `0x18000dd84`
- `0x18000ec14`

## string_xrefs

- `0x18000dd96`: `WLIDCCreateContextEx`

## pseudocode

```c
__int64 __fastcall TranslateRpcServiceError(unsigned int a1, const char *a2)
{
  unsigned int v2; // ebx
  int v3; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  const char *v7; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  bool v9; // [rsp+40h] [rbp+10h] BYREF
  const char *v10; // [rsp+48h] [rbp+18h] BYREF
  unsigned int v11; // [rsp+50h] [rbp+20h] BYREF

  v10 = a2;
  v2 = a1;
  v7 = "WLIDCCreateContextEx";
  if ( a1 == -2147023179 || a1 == -2147023174 || a1 == -2147023173 || a1 == -2147023170 || a1 == -2147023143 )
  {
    v9 = 1;
    v11 = -1;
    LODWORD(v10) = -1;
    v3 = QueryWlidsvcProperties(&v11, (unsigned int *)&v10, &v9);
    if ( v3 >= 0 )
    {
      MSAClientTraceTelemetry::RPCServerUnavailable<char const * &,bool &,unsigned long &,unsigned long &>(
        &v7,
        &v9,
        (int *)&v10,
        (int *)&v11);
      if ( !v9 )
        return 2147943660LL;
      if ( (_DWORD)v10 == 4 )
        return (unsigned int)-2147023838;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(retaddr, v4, v5, (const char *)(unsigned int)v3, (int)v7);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000dd84  mov     [rsp-8+arg_18], rbx
0x18000dd89  mov     [rsp-8+arg_8], rdx
0x18000dd8e  push    rbp
0x18000dd8f  mov     rbp, rsp
0x18000dd92  sub     rsp, 30h
0x18000dd96  lea     rax, aWlidccreatecon; "WLIDCCreateContextEx"
0x18000dd9d  mov     ebx, ecx
0x18000dd9f  mov     [rbp+var_10], rax
0x18000dda3  cmp     ecx, 800706B5h
0x18000dda9  jz      short loc_18000DDCB
0x18000ddab  cmp     ecx, 800706BAh
0x18000ddb1  jz      short loc_18000DDCB
0x18000ddb3  cmp     ecx, 800706BBh
0x18000ddb9  jz      short loc_18000DDCB
0x18000ddbb  cmp     ecx, 800706BEh
0x18000ddc1  jz      short loc_18000DDCB
0x18000ddc3  cmp     ecx, 800706D9h
0x18000ddc9  jnz     short loc_18000DE29
0x18000ddcb  or      eax, 0FFFFFFFFh
0x18000ddce  mov     [rbp+arg_0], 1
0x18000ddd2  lea     r8, [rbp+arg_0]; bool *
0x18000ddd6  mov     [rbp+arg_10], eax
0x18000ddd9  lea     rdx, [rbp+arg_8]; unsigned int *
0x18000dddd  mov     dword ptr [rbp+arg_8], eax
0x18000dde0  lea     rcx, [rbp+arg_10]; unsigned int *
0x18000dde4  call    ?QueryWlidsvcProperties@@YAJAEAK0AEA_N@Z; QueryWlidsvcProperties(ulong &,ulong &,bool &)
0x18000dde9  test    eax, eax
0x18000ddeb  jns     short loc_18000DDFB
0x18000dded  mov     rcx, [rbp+8]; this
0x18000ddf1  mov     r9d, eax; char *
0x18000ddf4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ddf9  jmp     short loc_18000DE29
0x18000ddfb  lea     r9, [rbp+arg_10]
0x18000ddff  lea     r8, [rbp+arg_8]
0x18000de03  lea     rdx, [rbp+arg_0]
0x18000de07  lea     rcx, [rbp+var_10]
0x18000de0b  call    ??$RPCServerUnavailable@AEAPEBDAEA_NAEAKAEAK@MSAClientTraceTelemetry@@SAXAEAPEBDAEA_NAEAK2@Z; MSAClientTraceTelemetry::RPCServerUnavailable<char const * &,bool &,ulong &,ulong &>(char const * &,bool &,ulong &,ulong &)
0x18000de10  cmp     [rbp+arg_0], 0
0x18000de14  jnz     short loc_18000DE1D
0x18000de16  mov     eax, 800704ECh
0x18000de1b  jmp     short loc_18000DE2B
0x18000de1d  cmp     dword ptr [rbp+arg_8], 4
0x18000de21  mov     eax, 80070422h
0x18000de26  cmovz   ebx, eax
0x18000de29  mov     eax, ebx
0x18000de2b  mov     rbx, [rsp+30h+arg_18]
0x18000de30  add     rsp, 30h
0x18000de34  pop     rbp
0x18000de35  retn
```
