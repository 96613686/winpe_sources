# CWerComReport::_get_LegacyBucketId(ushort * *)

- ea: `0x180010734`
- end: `0x1800108eb`
- name: `?_get_LegacyBucketId@CWerComReport@@QEAAJPEAPEAG@Z`
- size: `439`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011740`

## callees

- `0x180002850`
- `0x180006c9c`
- `0x180008f1c`
- `0x18000e35c`
- `0x180010734`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180010851`
- `OLEAUT32!__imp_SysAllocString` at `0x180010851`
- `OLEAUT32!__imp_SysFreeString` at `0x180010848`
- `OLEAUT32!__imp_SysFreeString` at `0x180010848`
- `wer!WerpGetLegacyBucketId` at `0x1800107d8`
- `wer!WerpGetLegacyBucketId` at `0x1800107d8`
- `wer!WerpDestroyWerString` at `0x1800107bb`
- `wer!WerpDestroyWerString` at `0x180010835`
- `wer!WerpDestroyWerString` at `0x1800108aa`
- `wer!WerpDestroyWerString` at `0x1800108d6`
- `wer!WerpDestroyWerString` at `0x1800107bb`
- `wer!WerpDestroyWerString` at `0x180010835`
- `wer!WerpDestroyWerString` at `0x1800108aa`
- `wer!WerpDestroyWerString` at `0x1800108d6`
- `wer!WerpGetWerStringData` at `0x180010808`
- `wer!WerpGetWerStringData` at `0x180010808`

## pseudocode

```c
__int64 __fastcall CWerComReport::_get_LegacyBucketId(CWerComReport *this, unsigned __int16 **a2)
{
  int WerApiLock; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v8; // rax
  const OLECHAR *WerStringData; // rbx
  unsigned __int16 *v10; // rax
  __int64 v11; // [rsp+50h] [rbp+30h] BYREF
  __int64 v12; // [rsp+58h] [rbp+38h] BYREF

  v11 = 0;
  v12 = 0;
  WerApiLock = CWerApiAutoLock::TryGetWerApiLock((CWerApiAutoLock *)&v12, this);
  if ( WerApiLock < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v6 = 46;
LABEL_5:
    WPP_SF_d(v5[2], v6, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids, (unsigned int)WerApiLock);
LABEL_6:
    if ( v12 )
      _InterlockedExchange((volatile __int32 *)(v12 + 48), 0);
    if ( v11 )
    {
      v12 = v11;
      WerpDestroyWerString(&v12);
    }
    return (unsigned int)WerApiLock;
  }
  v8 = utl::replace<void,werstring_deleter>(&v11);
  WerApiLock = WerpGetLegacyBucketId(*((_QWORD *)this + 4), v8);
  if ( WerApiLock < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v6 = 47;
    goto LABEL_5;
  }
  WerStringData = (const OLECHAR *)WerpGetWerStringData(v11);
  if ( WerStringData )
  {
    SysFreeString(*a2);
    v10 = SysAllocString(WerStringData);
    *a2 = v10;
    if ( v10 )
    {
      if ( v12 )
        _InterlockedExchange((volatile __int32 *)(v12 + 48), 0);
      if ( v11 )
      {
        v12 = v11;
        WerpDestroyWerString(&v12);
      }
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
      if ( v12 )
        _InterlockedExchange((volatile __int32 *)(v12 + 48), 0);
      if ( v11 )
      {
        v12 = v11;
        WerpDestroyWerString(&v12);
      }
      return 2147942414LL;
    }
  }
  else
  {
    if ( v12 )
      _InterlockedExchange((volatile __int32 *)(v12 + 48), 0);
    if ( v11 )
    {
      v12 = v11;
      WerpDestroyWerString(&v12);
    }
    return 2147943568LL;
  }
}

```

## disassembly

```asm
0x180010734  mov     [rsp-18h+arg_0], rbx
0x180010739  push    rbp
0x18001073a  push    rsi
0x18001073b  push    rdi
0x18001073c  mov     rbp, rsp
0x18001073f  sub     rsp, 20h
0x180010743  mov     rdi, rdx
0x180010746  mov     [rbp+arg_10], 0
0x18001074e  mov     rdx, rcx; struct CWerComReport *
0x180010751  mov     [rbp+arg_18], 0
0x180010759  mov     rsi, rcx
0x18001075c  lea     rcx, [rbp+arg_18]; this
0x180010760  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x180010765  mov     ebx, eax
0x180010767  test    eax, eax
0x180010769  jns     short loc_1800107C8
0x18001076b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010772  lea     rdx, WPP_GLOBAL_Control
0x180010779  cmp     rcx, rdx
0x18001077c  jz      short loc_18001079C
0x18001077e  test    byte ptr [rcx+1Ch], 1
0x180010782  jz      short loc_18001079C
0x180010784  mov     edx, 2Eh ; '.'
0x180010789  mov     rcx, [rcx+10h]
0x18001078d  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x180010794  mov     r9d, ebx
0x180010797  call    WPP_SF_d
0x18001079c  mov     rax, [rbp+arg_18]
0x1800107a0  test    rax, rax
0x1800107a3  jz      short loc_1800107AA
0x1800107a5  xor     ecx, ecx
0x1800107a7  xchg    ecx, [rax+30h]
0x1800107aa  mov     rax, [rbp+arg_10]
0x1800107ae  test    rax, rax
0x1800107b1  jz      short loc_1800107C1
0x1800107b3  lea     rcx, [rbp+arg_18]
0x1800107b7  mov     [rbp+arg_18], rax
0x1800107bb  call    cs:__imp_WerpDestroyWerString
0x1800107c1  mov     eax, ebx
0x1800107c3  jmp     loc_1800108DE
0x1800107c8  lea     rcx, [rbp+arg_10]
0x1800107cc  call    ??$replace@XUwerstring_deleter@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XUwerstring_deleter@@@0@@Z; utl::replace<void,werstring_deleter>(utl::unique_ptr<void,werstring_deleter> &)
0x1800107d1  mov     rcx, [rsi+20h]
0x1800107d5  mov     rdx, rax
0x1800107d8  call    cs:__imp_WerpGetLegacyBucketId
0x1800107de  mov     ebx, eax
0x1800107e0  test    eax, eax
0x1800107e2  jns     short loc_180010804
0x1800107e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107eb  lea     rdx, WPP_GLOBAL_Control
0x1800107f2  cmp     rcx, rdx
0x1800107f5  jz      short loc_18001079C
0x1800107f7  test    byte ptr [rcx+1Ch], 1
0x1800107fb  jz      short loc_18001079C
0x1800107fd  mov     edx, 2Fh ; '/'
0x180010802  jmp     short loc_180010789
0x180010804  mov     rcx, [rbp+arg_10]
0x180010808  call    cs:__imp_WerpGetWerStringData
0x18001080e  mov     rbx, rax
0x180010811  test    rax, rax
0x180010814  jnz     short loc_180010845
0x180010816  mov     rax, [rbp+arg_18]
0x18001081a  test    rax, rax
0x18001081d  jz      short loc_180010824
0x18001081f  xor     ecx, ecx
0x180010821  xchg    ecx, [rax+30h]
0x180010824  mov     rax, [rbp+arg_10]
0x180010828  test    rax, rax
0x18001082b  jz      short loc_18001083B
0x18001082d  lea     rcx, [rbp+arg_18]
0x180010831  mov     [rbp+arg_18], rax
0x180010835  call    cs:__imp_WerpDestroyWerString
0x18001083b  mov     eax, 80070490h
0x180010840  jmp     loc_1800108DE
0x180010845  mov     rcx, [rdi]; bstrString
0x180010848  call    cs:__imp_SysFreeString
0x18001084e  mov     rcx, rbx; psz
0x180010851  call    cs:__imp_SysAllocString
0x180010857  mov     [rdi], rax
0x18001085a  test    rax, rax
0x18001085d  jnz     short loc_1800108B7
0x18001085f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010866  lea     rdx, WPP_GLOBAL_Control
0x18001086d  cmp     rcx, rdx
0x180010870  jz      short loc_18001088B
0x180010872  test    byte ptr [rcx+1Ch], 1
0x180010876  jz      short loc_18001088B
0x180010878  mov     rcx, [rcx+10h]
0x18001087c  lea     edx, [rax+30h]
0x18001087f  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x180010886  call    WPP_SF_
0x18001088b  mov     rax, [rbp+arg_18]
0x18001088f  test    rax, rax
0x180010892  jz      short loc_180010899
0x180010894  xor     ecx, ecx
0x180010896  xchg    ecx, [rax+30h]
0x180010899  mov     rax, [rbp+arg_10]
0x18001089d  test    rax, rax
0x1800108a0  jz      short loc_1800108B0
0x1800108a2  lea     rcx, [rbp+arg_18]
0x1800108a6  mov     [rbp+arg_18], rax
0x1800108aa  call    cs:__imp_WerpDestroyWerString
0x1800108b0  mov     eax, 8007000Eh
0x1800108b5  jmp     short loc_1800108DE
0x1800108b7  mov     rax, [rbp+arg_18]
0x1800108bb  test    rax, rax
0x1800108be  jz      short loc_1800108C5
0x1800108c0  xor     ecx, ecx
0x1800108c2  xchg    ecx, [rax+30h]
0x1800108c5  mov     rax, [rbp+arg_10]
0x1800108c9  test    rax, rax
0x1800108cc  jz      short loc_1800108DC
0x1800108ce  lea     rcx, [rbp+arg_18]
0x1800108d2  mov     [rbp+arg_18], rax
0x1800108d6  call    cs:__imp_WerpDestroyWerString
0x1800108dc  xor     eax, eax
0x1800108de  mov     rbx, [rsp+20h+arg_0]
0x1800108e3  add     rsp, 20h
0x1800108e7  pop     rdi
0x1800108e8  pop     rsi
0x1800108e9  pop     rbp
0x1800108ea  retn
```
