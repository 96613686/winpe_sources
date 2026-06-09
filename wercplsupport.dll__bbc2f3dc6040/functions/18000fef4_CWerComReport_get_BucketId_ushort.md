# CWerComReport::_get_BucketId(ushort * *)

- ea: `0x18000fef4`
- end: `0x1800100ab`
- name: `?_get_BucketId@CWerComReport@@QEAAJPEAPEAG@Z`
- size: `439`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011120`

## callees

- `0x180002850`
- `0x180006c9c`
- `0x180008f1c`
- `0x18000e35c`
- `0x18000fef4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180010011`
- `OLEAUT32!__imp_SysAllocString` at `0x180010011`
- `OLEAUT32!__imp_SysFreeString` at `0x180010008`
- `OLEAUT32!__imp_SysFreeString` at `0x180010008`
- `wer!WerpGetBucketId` at `0x18000ff98`
- `wer!WerpGetBucketId` at `0x18000ff98`
- `wer!WerpDestroyWerString` at `0x18000ff7b`
- `wer!WerpDestroyWerString` at `0x18000fff5`
- `wer!WerpDestroyWerString` at `0x18001006a`
- `wer!WerpDestroyWerString` at `0x180010096`
- `wer!WerpDestroyWerString` at `0x18000ff7b`
- `wer!WerpDestroyWerString` at `0x18000fff5`
- `wer!WerpDestroyWerString` at `0x18001006a`
- `wer!WerpDestroyWerString` at `0x180010096`
- `wer!WerpGetWerStringData` at `0x18000ffc8`
- `wer!WerpGetWerStringData` at `0x18000ffc8`

## pseudocode

```c
__int64 __fastcall CWerComReport::_get_BucketId(CWerComReport *this, unsigned __int16 **a2)
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
    v6 = 43;
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
  WerApiLock = WerpGetBucketId(*((_QWORD *)this + 4), v8);
  if ( WerApiLock < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v6 = 44;
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
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
0x18000fef4  mov     [rsp-18h+arg_0], rbx
0x18000fef9  push    rbp
0x18000fefa  push    rsi
0x18000fefb  push    rdi
0x18000fefc  mov     rbp, rsp
0x18000feff  sub     rsp, 20h
0x18000ff03  mov     rdi, rdx
0x18000ff06  mov     [rbp+arg_10], 0
0x18000ff0e  mov     rdx, rcx; struct CWerComReport *
0x18000ff11  mov     [rbp+arg_18], 0
0x18000ff19  mov     rsi, rcx
0x18000ff1c  lea     rcx, [rbp+arg_18]; this
0x18000ff20  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x18000ff25  mov     ebx, eax
0x18000ff27  test    eax, eax
0x18000ff29  jns     short loc_18000FF88
0x18000ff2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff32  lea     rdx, WPP_GLOBAL_Control
0x18000ff39  cmp     rcx, rdx
0x18000ff3c  jz      short loc_18000FF5C
0x18000ff3e  test    byte ptr [rcx+1Ch], 1
0x18000ff42  jz      short loc_18000FF5C
0x18000ff44  mov     edx, 2Bh ; '+'
0x18000ff49  mov     rcx, [rcx+10h]
0x18000ff4d  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000ff54  mov     r9d, ebx
0x18000ff57  call    WPP_SF_d
0x18000ff5c  mov     rax, [rbp+arg_18]
0x18000ff60  test    rax, rax
0x18000ff63  jz      short loc_18000FF6A
0x18000ff65  xor     ecx, ecx
0x18000ff67  xchg    ecx, [rax+30h]
0x18000ff6a  mov     rax, [rbp+arg_10]
0x18000ff6e  test    rax, rax
0x18000ff71  jz      short loc_18000FF81
0x18000ff73  lea     rcx, [rbp+arg_18]
0x18000ff77  mov     [rbp+arg_18], rax
0x18000ff7b  call    cs:__imp_WerpDestroyWerString
0x18000ff81  mov     eax, ebx
0x18000ff83  jmp     loc_18001009E
0x18000ff88  lea     rcx, [rbp+arg_10]
0x18000ff8c  call    ??$replace@XUwerstring_deleter@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XUwerstring_deleter@@@0@@Z; utl::replace<void,werstring_deleter>(utl::unique_ptr<void,werstring_deleter> &)
0x18000ff91  mov     rcx, [rsi+20h]
0x18000ff95  mov     rdx, rax
0x18000ff98  call    cs:__imp_WerpGetBucketId
0x18000ff9e  mov     ebx, eax
0x18000ffa0  test    eax, eax
0x18000ffa2  jns     short loc_18000FFC4
0x18000ffa4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ffab  lea     rdx, WPP_GLOBAL_Control
0x18000ffb2  cmp     rcx, rdx
0x18000ffb5  jz      short loc_18000FF5C
0x18000ffb7  test    byte ptr [rcx+1Ch], 1
0x18000ffbb  jz      short loc_18000FF5C
0x18000ffbd  mov     edx, 2Ch ; ','
0x18000ffc2  jmp     short loc_18000FF49
0x18000ffc4  mov     rcx, [rbp+arg_10]
0x18000ffc8  call    cs:__imp_WerpGetWerStringData
0x18000ffce  mov     rbx, rax
0x18000ffd1  test    rax, rax
0x18000ffd4  jnz     short loc_180010005
0x18000ffd6  mov     rax, [rbp+arg_18]
0x18000ffda  test    rax, rax
0x18000ffdd  jz      short loc_18000FFE4
0x18000ffdf  xor     ecx, ecx
0x18000ffe1  xchg    ecx, [rax+30h]
0x18000ffe4  mov     rax, [rbp+arg_10]
0x18000ffe8  test    rax, rax
0x18000ffeb  jz      short loc_18000FFFB
0x18000ffed  lea     rcx, [rbp+arg_18]
0x18000fff1  mov     [rbp+arg_18], rax
0x18000fff5  call    cs:__imp_WerpDestroyWerString
0x18000fffb  mov     eax, 80070490h
0x180010000  jmp     loc_18001009E
0x180010005  mov     rcx, [rdi]; bstrString
0x180010008  call    cs:__imp_SysFreeString
0x18001000e  mov     rcx, rbx; psz
0x180010011  call    cs:__imp_SysAllocString
0x180010017  mov     [rdi], rax
0x18001001a  test    rax, rax
0x18001001d  jnz     short loc_180010077
0x18001001f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010026  lea     rdx, WPP_GLOBAL_Control
0x18001002d  cmp     rcx, rdx
0x180010030  jz      short loc_18001004B
0x180010032  test    byte ptr [rcx+1Ch], 1
0x180010036  jz      short loc_18001004B
0x180010038  mov     rcx, [rcx+10h]
0x18001003c  lea     edx, [rax+2Dh]
0x18001003f  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x180010046  call    WPP_SF_
0x18001004b  mov     rax, [rbp+arg_18]
0x18001004f  test    rax, rax
0x180010052  jz      short loc_180010059
0x180010054  xor     ecx, ecx
0x180010056  xchg    ecx, [rax+30h]
0x180010059  mov     rax, [rbp+arg_10]
0x18001005d  test    rax, rax
0x180010060  jz      short loc_180010070
0x180010062  lea     rcx, [rbp+arg_18]
0x180010066  mov     [rbp+arg_18], rax
0x18001006a  call    cs:__imp_WerpDestroyWerString
0x180010070  mov     eax, 8007000Eh
0x180010075  jmp     short loc_18001009E
0x180010077  mov     rax, [rbp+arg_18]
0x18001007b  test    rax, rax
0x18001007e  jz      short loc_180010085
0x180010080  xor     ecx, ecx
0x180010082  xchg    ecx, [rax+30h]
0x180010085  mov     rax, [rbp+arg_10]
0x180010089  test    rax, rax
0x18001008c  jz      short loc_18001009C
0x18001008e  lea     rcx, [rbp+arg_18]
0x180010092  mov     [rbp+arg_18], rax
0x180010096  call    cs:__imp_WerpDestroyWerString
0x18001009c  xor     eax, eax
0x18001009e  mov     rbx, [rsp+20h+arg_0]
0x1800100a3  add     rsp, 20h
0x1800100a7  pop     rdi
0x1800100a8  pop     rsi
0x1800100a9  pop     rbp
0x1800100aa  retn
```
