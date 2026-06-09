# TrkReportInternalError(ulong,ulong,long,ushort const *)

- ea: `0x18000feb0`
- end: `0x18000ffba`
- name: `?TrkReportInternalError@@YAJKKJPEBG@Z`
- size: `266`
- prototype: `__int64 __fastcall(int, int, unsigned int, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180001cb8`
- `0x180009364`
- `0x18000a65c`
- `0x18000a880`
- `0x18000a9d0`
- `0x18000aacc`

## callees

- `0x18000b520`
- `0x18000feb0`
- `0x1800100f0`
- `0x180010fca`
- `0x180011000`

## pseudocode

```c
__int64 __fastcall TrkReportInternalError(int a1, int a2, unsigned int a3, const unsigned __int16 *a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rcx
  _WORD *v10; // rax
  const unsigned __int16 *v11; // r8
  __int64 v12; // rdx
  _WORD *v13; // rcx
  __int64 v14; // rax
  _DWORD v16[2]; // [rsp+30h] [rbp-268h] BYREF
  _BYTE v17[536]; // [rsp+38h] [rbp-260h] BYREF
  unsigned __int16 v18[12]; // [rsp+250h] [rbp-48h] BYREF

  memset_0(v17, 0, 0x20Cu);
  v16[0] = a1;
  v8 = 8;
  v16[1] = a2;
  if ( a4 )
  {
    v9 = 260;
    v10 = v17;
    v11 = a4;
    v12 = 261;
    do
    {
      if ( !v9 )
        break;
      if ( !*v11 )
        break;
      *v10++ = *v11++;
      --v9;
      --v12;
    }
    while ( v12 );
    v13 = v10 - 1;
    if ( v12 )
      v13 = v10;
    v14 = -1;
    *v13 = 0;
    do
      ++v14;
    while ( a4[v14] );
    v8 = 2 * v14 + 8;
  }
  StringCchPrintfW(v18, 9u, L"%08x", a3);
  return TrkReportRawEventWrapper(0xC00030D4, 1u, v8, v16, v18, 0);
}

```

## disassembly

```asm
0x18000feb0  push    rbx
0x18000feb2  push    rbp
0x18000feb3  push    rsi
0x18000feb4  push    rdi
0x18000feb5  push    r14
0x18000feb7  sub     rsp, 270h
0x18000febe  mov     rax, cs:__security_cookie
0x18000fec5  xor     rax, rsp
0x18000fec8  mov     [rsp+298h+var_30], rax
0x18000fed0  mov     ebp, r8d
0x18000fed3  mov     edi, edx
0x18000fed5  mov     ebx, ecx
0x18000fed7  xor     edx, edx; Val
0x18000fed9  mov     r8d, 20Ch; Size
0x18000fedf  lea     rcx, [rsp+298h+var_260]; void *
0x18000fee4  mov     rsi, r9
0x18000fee7  call    memset_0
0x18000feec  mov     [rsp+298h+var_268], ebx
0x18000fef0  mov     ebx, 8
0x18000fef5  mov     [rsp+298h+var_264], edi
0x18000fef9  xor     edi, edi
0x18000fefb  lea     r14d, [rbx-7]
0x18000feff  test    rsi, rsi
0x18000ff02  jz      short loc_18000FF59
0x18000ff04  mov     ecx, 104h
0x18000ff09  lea     rax, [rsp+298h+var_260]
0x18000ff0e  mov     r8, rsi
0x18000ff11  lea     edx, [rcx+1]
0x18000ff14  test    rcx, rcx
0x18000ff17  jz      short loc_18000FF37
0x18000ff19  movzx   r9d, word ptr [r8]
0x18000ff1d  test    r9w, r9w
0x18000ff21  jz      short loc_18000FF37
0x18000ff23  mov     [rax], r9w
0x18000ff27  add     r8, 2
0x18000ff2b  add     rax, 2
0x18000ff2f  sub     rcx, r14
0x18000ff32  sub     rdx, r14
0x18000ff35  jnz     short loc_18000FF14
0x18000ff37  test    rdx, rdx
0x18000ff3a  lea     rcx, [rax-2]
0x18000ff3e  cmovnz  rcx, rax
0x18000ff42  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ff46  mov     [rcx], di
0x18000ff49  inc     rax
0x18000ff4c  cmp     [rsi+rax*2], di
0x18000ff50  jnz     short loc_18000FF49
0x18000ff52  lea     ebx, ds:8[rax*2]
0x18000ff59  mov     r9d, ebp
0x18000ff5c  lea     r8, a08x; "%08x"
0x18000ff63  mov     edx, 9; unsigned __int64
0x18000ff68  lea     rcx, [rsp+298h+var_48]; unsigned __int16 *
0x18000ff70  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ff75  lea     rax, [rsp+298h+var_48]
0x18000ff7d  mov     [rsp+298h+var_270], rdi
0x18000ff82  lea     r9, [rsp+298h+var_268]; void *
0x18000ff87  mov     [rsp+298h+var_278], rax
0x18000ff8c  mov     r8d, ebx; unsigned int
0x18000ff8f  mov     edx, r14d; unsigned __int16
0x18000ff92  mov     ecx, 0C00030D4h; unsigned int
0x18000ff97  call    ?TrkReportRawEventWrapper@@YAJKGKPEBXZZ; TrkReportRawEventWrapper(ulong,ushort,ulong,void const *,...)
0x18000ff9c  mov     rcx, [rsp+298h+var_30]
0x18000ffa4  xor     rcx, rsp; StackCookie
0x18000ffa7  call    __security_check_cookie
0x18000ffac  add     rsp, 270h
0x18000ffb3  pop     r14
0x18000ffb5  pop     rdi
0x18000ffb6  pop     rsi
0x18000ffb7  pop     rbp
0x18000ffb8  pop     rbx
0x18000ffb9  retn
```
