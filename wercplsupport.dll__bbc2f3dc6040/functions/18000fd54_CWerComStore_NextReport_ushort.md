# CWerComStore::_NextReport(ushort * *)

- ea: `0x18000fd54`
- end: `0x18000fec4`
- name: `?_NextReport@CWerComStore@@QEAAJPEAPEAG@Z`
- size: `368`
- prototype: `__int64 __fastcall(CWerComStore *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000c180`

## callees

- `0x180002850`
- `0x180006c9c`
- `0x180008f1c`
- `0x18000e3fc`
- `0x18000fd54`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000fe2a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fe2a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fe17`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fe17`
- `wer!WerpEnumerateStoreNext` at `0x18000fde1`
- `wer!WerpEnumerateStoreNext` at `0x18000fde1`
- `wer!WerpDestroyWerString` at `0x18000fdfe`
- `wer!WerpDestroyWerString` at `0x18000fe75`
- `wer!WerpDestroyWerString` at `0x18000fea1`
- `wer!WerpDestroyWerString` at `0x18000fdfe`
- `wer!WerpDestroyWerString` at `0x18000fe75`
- `wer!WerpDestroyWerString` at `0x18000fea1`
- `wer!WerpGetWerStringData` at `0x18000fe21`
- `wer!WerpGetWerStringData` at `0x18000fe21`

## pseudocode

```c
__int64 __fastcall CWerComStore::_NextReport(CWerComStore *this, unsigned __int16 **a2)
{
  int WerStoreApiLock; // eax
  int v5; // ebx
  __int64 v7; // rax
  const OLECHAR *WerStringData; // rax
  unsigned __int16 *v9; // rax
  _QWORD v10[2]; // [rsp+20h] [rbp-10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+30h] BYREF
  __int64 v12; // [rsp+68h] [rbp+38h] BYREF

  v12 = 0;
  WerStoreApiLock = CWerStoreApiAutoLock::TryGetWerStoreApiLock((CWerStoreApiAutoLock *)&v12, this);
  v5 = WerStoreApiLock;
  if ( WerStoreApiLock < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
        (unsigned int)WerStoreApiLock);
    if ( v12 )
      _InterlockedExchange((volatile __int32 *)(v12 + 40), 0);
    return (unsigned int)v5;
  }
  v11 = 0;
  v7 = utl::replace<void,werstring_deleter>(&v11);
  v5 = WerpEnumerateStoreNext(*((_QWORD *)this + 4), v7);
  if ( v5 < 0 )
  {
    if ( v11 )
    {
      v10[0] = v11;
      WerpDestroyWerString(v10);
    }
    if ( v12 )
      _InterlockedExchange((volatile __int32 *)(v12 + 40), 0);
    return (unsigned int)v5;
  }
  SysFreeString(*a2);
  WerStringData = (const OLECHAR *)WerpGetWerStringData(v11);
  v9 = SysAllocString(WerStringData);
  *a2 = v9;
  if ( v9 )
  {
    if ( v11 )
    {
      v10[0] = v11;
      WerpDestroyWerString(v10);
    }
    if ( v12 )
      _InterlockedExchange((volatile __int32 *)(v12 + 40), 0);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    if ( v11 )
    {
      v10[0] = v11;
      WerpDestroyWerString(v10);
    }
    if ( v12 )
      _InterlockedExchange((volatile __int32 *)(v12 + 40), 0);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000fd54  mov     [rsp-18h+arg_0], rbx
0x18000fd59  push    rbp
0x18000fd5a  push    rsi
0x18000fd5b  push    rdi
0x18000fd5c  mov     rbp, rsp
0x18000fd5f  sub     rsp, 30h
0x18000fd63  mov     rsi, rdx
0x18000fd66  mov     [rbp+arg_18], 0
0x18000fd6e  mov     rdx, rcx; struct CWerComStore *
0x18000fd71  mov     rdi, rcx
0x18000fd74  lea     rcx, [rbp+arg_18]; this
0x18000fd78  call    ?TryGetWerStoreApiLock@CWerStoreApiAutoLock@@QEAAJPEAVCWerComStore@@@Z; CWerStoreApiAutoLock::TryGetWerStoreApiLock(CWerComStore *)
0x18000fd7d  mov     ebx, eax
0x18000fd7f  test    eax, eax
0x18000fd81  jns     short loc_18000FDC9
0x18000fd83  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd8a  lea     rdx, WPP_GLOBAL_Control
0x18000fd91  cmp     rcx, rdx
0x18000fd94  jz      short loc_18000FDB4
0x18000fd96  test    byte ptr [rcx+1Ch], 1
0x18000fd9a  jz      short loc_18000FDB4
0x18000fd9c  mov     rcx, [rcx+10h]
0x18000fda0  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000fda7  mov     edx, 56h ; 'V'
0x18000fdac  mov     r9d, eax
0x18000fdaf  call    WPP_SF_d
0x18000fdb4  mov     rax, [rbp+arg_18]
0x18000fdb8  test    rax, rax
0x18000fdbb  jz      short loc_18000FDC2
0x18000fdbd  xor     ecx, ecx
0x18000fdbf  xchg    ecx, [rax+28h]
0x18000fdc2  mov     eax, ebx
0x18000fdc4  jmp     loc_18000FEB7
0x18000fdc9  lea     rcx, [rbp+arg_10]
0x18000fdcd  mov     [rbp+arg_10], 0
0x18000fdd5  call    ??$replace@XUwerstring_deleter@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XUwerstring_deleter@@@0@@Z; utl::replace<void,werstring_deleter>(utl::unique_ptr<void,werstring_deleter> &)
0x18000fdda  mov     rcx, [rdi+20h]
0x18000fdde  mov     rdx, rax
0x18000fde1  call    cs:__imp_WerpEnumerateStoreNext
0x18000fde7  mov     ebx, eax
0x18000fde9  test    eax, eax
0x18000fdeb  jns     short loc_18000FE14
0x18000fded  mov     rcx, [rbp+arg_10]
0x18000fdf1  test    rcx, rcx
0x18000fdf4  jz      short loc_18000FE04
0x18000fdf6  mov     [rbp+var_10], rcx
0x18000fdfa  lea     rcx, [rbp+var_10]
0x18000fdfe  call    cs:__imp_WerpDestroyWerString
0x18000fe04  mov     rcx, [rbp+arg_18]
0x18000fe08  test    rcx, rcx
0x18000fe0b  jz      short loc_18000FDC2
0x18000fe0d  xor     eax, eax
0x18000fe0f  xchg    eax, [rcx+28h]
0x18000fe12  jmp     short loc_18000FDC2
0x18000fe14  mov     rcx, [rsi]; bstrString
0x18000fe17  call    cs:__imp_SysFreeString
0x18000fe1d  mov     rcx, [rbp+arg_10]
0x18000fe21  call    cs:__imp_WerpGetWerStringData
0x18000fe27  mov     rcx, rax; psz
0x18000fe2a  call    cs:__imp_SysAllocString
0x18000fe30  mov     [rsi], rax
0x18000fe33  test    rax, rax
0x18000fe36  jnz     short loc_18000FE90
0x18000fe38  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe3f  lea     rdx, WPP_GLOBAL_Control
0x18000fe46  cmp     rcx, rdx
0x18000fe49  jz      short loc_18000FE64
0x18000fe4b  test    byte ptr [rcx+1Ch], 1
0x18000fe4f  jz      short loc_18000FE64
0x18000fe51  mov     rcx, [rcx+10h]
0x18000fe55  lea     edx, [rax+57h]
0x18000fe58  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000fe5f  call    WPP_SF_
0x18000fe64  mov     rax, [rbp+arg_10]
0x18000fe68  test    rax, rax
0x18000fe6b  jz      short loc_18000FE7B
0x18000fe6d  lea     rcx, [rbp+var_10]
0x18000fe71  mov     [rbp+var_10], rax
0x18000fe75  call    cs:__imp_WerpDestroyWerString
0x18000fe7b  mov     rax, [rbp+arg_18]
0x18000fe7f  test    rax, rax
0x18000fe82  jz      short loc_18000FE89
0x18000fe84  xor     ecx, ecx
0x18000fe86  xchg    ecx, [rax+28h]
0x18000fe89  mov     eax, 8007000Eh
0x18000fe8e  jmp     short loc_18000FEB7
0x18000fe90  mov     rax, [rbp+arg_10]
0x18000fe94  test    rax, rax
0x18000fe97  jz      short loc_18000FEA7
0x18000fe99  lea     rcx, [rbp+var_10]
0x18000fe9d  mov     [rbp+var_10], rax
0x18000fea1  call    cs:__imp_WerpDestroyWerString
0x18000fea7  mov     rax, [rbp+arg_18]
0x18000feab  test    rax, rax
0x18000feae  jz      short loc_18000FEB5
0x18000feb0  xor     ecx, ecx
0x18000feb2  xchg    ecx, [rax+28h]
0x18000feb5  xor     eax, eax
0x18000feb7  mov     rbx, [rsp+30h+arg_0]
0x18000febc  add     rsp, 30h
0x18000fec0  pop     rdi
0x18000fec1  pop     rsi
0x18000fec2  pop     rbp
0x18000fec3  retn
```
