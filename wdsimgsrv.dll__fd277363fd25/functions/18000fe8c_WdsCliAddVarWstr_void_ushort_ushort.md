# WdsCliAddVarWstr(void *,ushort *,ushort *)

- ea: `0x18000fe8c`
- end: `0x18000ffb3`
- name: `?WdsCliAddVarWstr@@YAJPEAXPEAG1@Z`
- size: `295`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180002e64`
- `0x180003af4`
- `0x180006548`
- `0x180010860`

## callees

- `0x180006cd4`
- `0x18000fe8c`
- `0x18000ffbc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ff35`
- `KERNEL32!GetLastError` at `0x18000ff53`
- `KERNEL32!GetLastError` at `0x18000ff35`
- `KERNEL32!GetLastError` at `0x18000ff53`
- `WDSCSL!WdsCpParameterAdd` at `0x18000ff24`
- `WDSCSL!WdsCpParameterAdd` at `0x18000ff24`

## pseudocode

```c
__int64 __fastcall WdsCliAddVarWstr(void *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 v6; // rax
  unsigned __int64 v7; // rax
  unsigned int v8; // r14d
  __int64 v9; // rbx
  unsigned __int16 *v10; // rax
  signed int LastError; // eax
  bool v12; // sf
  signed int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8

  if ( a1 && a2 && a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    v7 = 2 * v6 + 2;
    v8 = -1;
    if ( v7 <= 0xFFFFFFFF )
      v8 = v7;
    LODWORD(v9) = v7 > 0xFFFFFFFF ? 0x80070216 : 0;
    if ( (int)ElValidateHr_3((unsigned int)v9, a2, a3, 214) >= 0 )
    {
      v10 = (unsigned __int16 *)WdsCpParameterAdd(a1, a2, 32);
      if ( v10 )
      {
        v9 = (unsigned int)StringCbCopyW(v10, v8, a3);
        ElValidateHr_3(v9, v14, v15, 224);
      }
      else
      {
        LastError = GetLastError();
        v12 = LastError < 0;
        if ( LastError > 0 )
          v12 = 1;
        if ( v12 )
        {
          v13 = GetLastError();
          LODWORD(v9) = v13;
          if ( v13 > 0 )
            LODWORD(v9) = (unsigned __int16)v13 | 0x80070000;
        }
        else
        {
          LODWORD(v9) = -2147467259;
        }
      }
    }
  }
  else
  {
    LODWORD(v9) = -2147024809;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000fe8c  mov     [rsp+arg_8], rbx
0x18000fe91  mov     [rsp+arg_10], rbp
0x18000fe96  mov     [rsp+arg_18], rsi
0x18000fe9b  push    rdi
0x18000fe9c  push    r14
0x18000fe9e  push    r15
0x18000fea0  sub     rsp, 30h
0x18000fea4  xor     r15d, r15d
0x18000fea7  mov     rdi, r8
0x18000feaa  mov     rsi, rdx
0x18000fead  mov     rbp, rcx
0x18000feb0  test    rcx, rcx
0x18000feb3  jz      loc_18000FF92
0x18000feb9  test    rdx, rdx
0x18000febc  jz      loc_18000FF92
0x18000fec2  test    r8, r8
0x18000fec5  jz      loc_18000FF92
0x18000fecb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fecf  inc     rax
0x18000fed2  cmp     [r8+rax*2], r15w
0x18000fed7  jnz     short loc_18000FECF
0x18000fed9  mov     ecx, 0FFFFFFFFh
0x18000fede  lea     rax, ds:2[rax*2]
0x18000fee6  cmp     rax, rcx
0x18000fee9  mov     r14d, ecx
0x18000feec  mov     r9d, 0D6h
0x18000fef2  cmovbe  r14d, eax
0x18000fef6  cmp     rcx, rax
0x18000fef9  sbb     ebx, ebx
0x18000fefb  and     ebx, 80070216h
0x18000ff01  mov     ecx, ebx
0x18000ff03  call    ElValidateHr_3
0x18000ff08  test    eax, eax
0x18000ff0a  js      loc_18000FF97
0x18000ff10  mov     r9d, r14d
0x18000ff13  mov     [rsp+48h+var_28], r15d
0x18000ff18  mov     r8d, 20h ; ' '
0x18000ff1e  mov     rdx, rsi
0x18000ff21  mov     rcx, rbp
0x18000ff24  call    cs:__imp_WdsCpParameterAdd
0x18000ff2b  nop     dword ptr [rax+rax+00h]
0x18000ff30  test    rax, rax
0x18000ff33  jnz     short loc_18000FF73
0x18000ff35  call    cs:__imp_GetLastError
0x18000ff3c  nop     dword ptr [rax+rax+00h]
0x18000ff41  mov     edi, 80070000h
0x18000ff46  test    eax, eax
0x18000ff48  jle     short loc_18000FF51
0x18000ff4a  movzx   eax, ax
0x18000ff4d  or      eax, edi
0x18000ff4f  test    eax, eax
0x18000ff51  jns     short loc_18000FF6C
0x18000ff53  call    cs:__imp_GetLastError
0x18000ff5a  nop     dword ptr [rax+rax+00h]
0x18000ff5f  mov     ebx, eax
0x18000ff61  test    eax, eax
0x18000ff63  jle     short loc_18000FF97
0x18000ff65  movzx   ebx, ax
0x18000ff68  or      ebx, edi
0x18000ff6a  jmp     short loc_18000FF97
0x18000ff6c  mov     ebx, 80004005h
0x18000ff71  jmp     short loc_18000FF97
0x18000ff73  mov     edx, r14d; unsigned __int64
0x18000ff76  mov     r8, rdi; unsigned __int16 *
0x18000ff79  mov     rcx, rax; unsigned __int16 *
0x18000ff7c  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ff81  mov     r9d, 0E0h
0x18000ff87  mov     ecx, eax
0x18000ff89  mov     ebx, eax
0x18000ff8b  call    ElValidateHr_3
0x18000ff90  jmp     short loc_18000FF97
0x18000ff92  mov     ebx, 80070057h
0x18000ff97  mov     rbp, [rsp+48h+arg_10]
0x18000ff9c  mov     eax, ebx
0x18000ff9e  mov     rbx, [rsp+48h+arg_8]
0x18000ffa3  mov     rsi, [rsp+48h+arg_18]
0x18000ffa8  add     rsp, 30h
0x18000ffac  pop     r15
0x18000ffae  pop     r14
0x18000ffb0  pop     rdi
0x18000ffb1  retn
```
