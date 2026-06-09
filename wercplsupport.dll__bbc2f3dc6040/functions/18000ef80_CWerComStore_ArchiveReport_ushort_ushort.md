# CWerComStore::_ArchiveReport(ushort *,ushort * *)

- ea: `0x18000ef80`
- end: `0x18000f13f`
- name: `?_ArchiveReport@CWerComStore@@QEAAJPEAGPEAPEAG@Z`
- size: `447`
- prototype: `__int64 __fastcall(CWerComStore *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a360`

## callees

- `0x180002850`
- `0x180006c9c`
- `0x180008f1c`
- `0x18000e3fc`
- `0x18000ef80`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000f097`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f097`
- `wer!WerpArchiveReport` at `0x18000f037`
- `wer!WerpArchiveReport` at `0x18000f037`
- `wer!WerpDestroyWerString` at `0x18000f11f`
- `wer!WerpDestroyWerString` at `0x18000f11f`
- `wer!WerpGetWerStringData` at `0x18000f089`
- `wer!WerpGetWerStringData` at `0x18000f089`

## pseudocode

```c
__int64 __fastcall CWerComStore::_ArchiveReport(CWerComStore *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  int WerStoreApiLock; // eax
  unsigned int v7; // ebx
  __int64 v8; // rax
  int v9; // eax
  const OLECHAR *WerStringData; // rax
  unsigned __int16 *v11; // rax
  __int64 v13; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v14[6]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v15; // [rsp+88h] [rbp+20h] BYREF

  v13 = 0;
  WerStoreApiLock = CWerStoreApiAutoLock::TryGetWerStoreApiLock((CWerStoreApiAutoLock *)&v13, this);
  v7 = WerStoreApiLock;
  if ( WerStoreApiLock >= 0 )
  {
    v15 = 0;
    if ( a2 && a3 )
    {
      *a3 = 0;
      v8 = utl::replace<void,werstring_deleter>(&v15);
      v9 = WerpArchiveReport(*((_QWORD *)this + 4), a2, 1, v8, 0);
      v7 = v9;
      if ( v9 >= 0 )
      {
        WerStringData = (const OLECHAR *)WerpGetWerStringData(v15);
        if ( WerStringData )
        {
          v11 = SysAllocString(WerStringData);
          *a3 = v11;
          if ( !v11
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
          }
        }
        v7 = 0;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          96,
          WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
          (unsigned int)v9);
      }
    }
    else
    {
      v7 = -2147024809;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    }
    if ( v15 )
    {
      v14[0] = v15;
      WerpDestroyWerString(v14);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      94,
      WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
      (unsigned int)WerStoreApiLock);
  }
  if ( v13 )
    _InterlockedExchange((volatile __int32 *)(v13 + 40), 0);
  return v7;
}

```

## disassembly

```asm
0x18000ef80  push    rbx
0x18000ef82  push    rbp
0x18000ef83  push    rsi
0x18000ef84  push    rdi
0x18000ef85  sub     rsp, 48h
0x18000ef89  mov     rsi, rdx
0x18000ef8c  mov     [rsp+68h+var_38], 0
0x18000ef95  mov     rdx, rcx; struct CWerComStore *
0x18000ef98  mov     rbp, rcx
0x18000ef9b  lea     rcx, [rsp+68h+var_38]; this
0x18000efa0  mov     rdi, r8
0x18000efa3  call    ?TryGetWerStoreApiLock@CWerStoreApiAutoLock@@QEAAJPEAVCWerComStore@@@Z; CWerStoreApiAutoLock::TryGetWerStoreApiLock(CWerComStore *)
0x18000efa8  mov     ebx, eax
0x18000efaa  test    eax, eax
0x18000efac  jns     short loc_18000EFEC
0x18000efae  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efb5  lea     rdx, WPP_GLOBAL_Control
0x18000efbc  cmp     rcx, rdx
0x18000efbf  jz      loc_18000F125
0x18000efc5  test    byte ptr [rcx+1Ch], 1
0x18000efc9  jz      loc_18000F125
0x18000efcf  mov     rcx, [rcx+10h]
0x18000efd3  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000efda  mov     edx, 5Eh ; '^'
0x18000efdf  mov     r9d, eax
0x18000efe2  call    WPP_SF_d
0x18000efe7  jmp     loc_18000F125
0x18000efec  mov     [rsp+68h+arg_18], 0
0x18000eff8  test    rsi, rsi
0x18000effb  jz      loc_18000F0D5
0x18000f001  test    rdi, rdi
0x18000f004  jz      loc_18000F0D5
0x18000f00a  lea     rcx, [rsp+68h+arg_18]
0x18000f012  mov     qword ptr [rdi], 0
0x18000f019  call    ??$replace@XUwerstring_deleter@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XUwerstring_deleter@@@0@@Z; utl::replace<void,werstring_deleter>(utl::unique_ptr<void,werstring_deleter> &)
0x18000f01e  mov     rcx, [rbp+20h]
0x18000f022  mov     r9, rax
0x18000f025  mov     r8d, 1
0x18000f02b  mov     [rsp+68h+var_48], 0
0x18000f034  mov     rdx, rsi
0x18000f037  call    cs:__imp_WerpArchiveReport
0x18000f03d  mov     ebx, eax
0x18000f03f  test    eax, eax
0x18000f041  jns     short loc_18000F081
0x18000f043  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f04a  lea     rdx, WPP_GLOBAL_Control
0x18000f051  cmp     rcx, rdx
0x18000f054  jz      loc_18000F108
0x18000f05a  test    byte ptr [rcx+1Ch], 1
0x18000f05e  jz      loc_18000F108
0x18000f064  mov     rcx, [rcx+10h]
0x18000f068  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000f06f  mov     edx, 60h ; '`'
0x18000f074  mov     r9d, eax
0x18000f077  call    WPP_SF_d
0x18000f07c  jmp     loc_18000F108
0x18000f081  mov     rcx, [rsp+68h+arg_18]
0x18000f089  call    cs:__imp_WerpGetWerStringData
0x18000f08f  test    rax, rax
0x18000f092  jz      short loc_18000F0D1
0x18000f094  mov     rcx, rax; psz
0x18000f097  call    cs:__imp_SysAllocString
0x18000f09d  mov     [rdi], rax
0x18000f0a0  test    rax, rax
0x18000f0a3  jnz     short loc_18000F0D1
0x18000f0a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0ac  lea     rdx, WPP_GLOBAL_Control
0x18000f0b3  cmp     rcx, rdx
0x18000f0b6  jz      short loc_18000F0D1
0x18000f0b8  test    byte ptr [rcx+1Ch], 1
0x18000f0bc  jz      short loc_18000F0D1
0x18000f0be  mov     rcx, [rcx+10h]
0x18000f0c2  lea     edx, [rax+61h]
0x18000f0c5  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000f0cc  call    WPP_SF_
0x18000f0d1  xor     ebx, ebx
0x18000f0d3  jmp     short loc_18000F108
0x18000f0d5  mov     ebx, 80070057h
0x18000f0da  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0e1  lea     rdx, WPP_GLOBAL_Control
0x18000f0e8  cmp     rcx, rdx
0x18000f0eb  jz      short loc_18000F108
0x18000f0ed  test    byte ptr [rcx+1Ch], 1
0x18000f0f1  jz      short loc_18000F108
0x18000f0f3  mov     rcx, [rcx+10h]
0x18000f0f7  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000f0fe  mov     edx, 5Fh ; '_'
0x18000f103  call    WPP_SF_
0x18000f108  mov     rax, [rsp+68h+arg_18]
0x18000f110  test    rax, rax
0x18000f113  jz      short loc_18000F125
0x18000f115  lea     rcx, [rsp+68h+var_30]
0x18000f11a  mov     [rsp+68h+var_30], rax
0x18000f11f  call    cs:__imp_WerpDestroyWerString
0x18000f125  mov     rax, [rsp+68h+var_38]
0x18000f12a  test    rax, rax
0x18000f12d  jz      short loc_18000F134
0x18000f12f  xor     ecx, ecx
0x18000f131  xchg    ecx, [rax+28h]
0x18000f134  mov     eax, ebx
0x18000f136  add     rsp, 48h
0x18000f13a  pop     rdi
0x18000f13b  pop     rsi
0x18000f13c  pop     rbp
0x18000f13d  pop     rbx
0x18000f13e  retn
```
