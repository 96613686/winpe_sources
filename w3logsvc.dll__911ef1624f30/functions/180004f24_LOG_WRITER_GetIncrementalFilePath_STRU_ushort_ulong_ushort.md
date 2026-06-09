# LOG_WRITER::GetIncrementalFilePath(STRU *,ushort *,ulong,ushort * *)

- ea: `0x180004f24`
- end: `0x180004fdd`
- name: `?GetIncrementalFilePath@LOG_WRITER@@AEAAJPEAVSTRU@@PEAGKPEAPEAG@Z`
- size: `185`
- prototype: `HRESULT __fastcall(PCWSTR *this, struct STRU *, unsigned __int16 *, unsigned int, unsigned __int16 **ppszPathOut)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004dbc`

## callees

- `0x180002b14`
- `0x180004f24`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180004fce`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180004fce`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004f5a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004f6e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004fae`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004f5a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004f6e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004fae`

## pseudocode

```c
HRESULT __fastcall LOG_WRITER::GetIncrementalFilePath(
        PCWSTR *this,
        struct STRU *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 **ppszPathOut)
{
  unsigned __int64 v5; // rsi
  HRESULT result; // eax
  LOG_WRITER *v10; // rcx

  v5 = a4;
  **((_WORD **)a2 + 4) = 0;
  *((_DWORD *)a2 + 12) = 0;
  if ( !*((_DWORD *)this[1] + 3) || (result = STRU::Append(a2, L"u_"), result >= 0) )
  {
    result = STRU::Append(a2, L"extend");
    if ( result >= 0 )
    {
      result = LOG_WRITER::AppendNum(v10, a2, v5, a3, 0xCu, 0, 0);
      if ( result >= 0 )
      {
        result = STRU::Append(a2, L"_x.log");
        if ( result >= 0 )
          return PathAllocCombine(this[13], *((PCWSTR *)a2 + 4), 1u, ppszPathOut);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004f24  push    rbx
0x180004f26  push    rbp
0x180004f27  push    rsi
0x180004f28  push    rdi
0x180004f29  sub     rsp, 48h
0x180004f2d  mov     r10, [rdx+20h]
0x180004f31  xor     eax, eax
0x180004f33  mov     esi, r9d
0x180004f36  mov     rbp, r8
0x180004f39  mov     rbx, rdx
0x180004f3c  mov     rdi, rcx
0x180004f3f  mov     [r10], ax
0x180004f43  mov     [rdx+30h], eax
0x180004f46  mov     rax, [rcx+8]
0x180004f4a  cmp     dword ptr [rax+0Ch], 0
0x180004f4e  jz      short loc_180004F64
0x180004f50  lea     rdx, aU; "u_"
0x180004f57  mov     rcx, rbx
0x180004f5a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004f60  test    eax, eax
0x180004f62  js      short loc_180004FD4
0x180004f64  lea     rdx, aExtend; "extend"
0x180004f6b  mov     rcx, rbx
0x180004f6e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004f74  test    eax, eax
0x180004f76  js      short loc_180004FD4
0x180004f78  mov     [rsp+68h+var_38], 0; int
0x180004f80  mov     r8, rsi; unsigned __int64
0x180004f83  mov     [rsp+68h+var_40], 0; unsigned __int16 *
0x180004f8c  mov     r9, rbp; unsigned __int16 *
0x180004f8f  mov     rdx, rbx; struct STRU *
0x180004f92  mov     [rsp+68h+var_48], 0Ch; unsigned __int64
0x180004f9b  call    ?AppendNum@LOG_WRITER@@AEAAJPEAVSTRU@@_KPEAG1PEBGH@Z; LOG_WRITER::AppendNum(STRU *,unsigned __int64,ushort *,unsigned __int64,ushort const *,int)
0x180004fa0  test    eax, eax
0x180004fa2  js      short loc_180004FD4
0x180004fa4  lea     rdx, aXLog; "_x.log"
0x180004fab  mov     rcx, rbx
0x180004fae  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004fb4  test    eax, eax
0x180004fb6  js      short loc_180004FD4
0x180004fb8  mov     r9, [rsp+68h+ppszPathOut]; ppszPathOut
0x180004fc0  mov     r8d, 1; dwFlags
0x180004fc6  mov     rdx, [rbx+20h]; pszMore
0x180004fca  mov     rcx, [rdi+68h]; pszPathIn
0x180004fce  call    cs:__imp_PathAllocCombine
0x180004fd4  add     rsp, 48h
0x180004fd8  pop     rdi
0x180004fd9  pop     rsi
0x180004fda  pop     rbp
0x180004fdb  pop     rbx
0x180004fdc  retn
```
