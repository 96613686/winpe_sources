# CWinInetHelperClass::GetAttributes(ulong *,tagHELPER_ATTRIBUTE * *)

- ea: `0x180004d60`
- end: `0x180004ef1`
- name: `?GetAttributes@CWinInetHelperClass@@UEAAJPEAKPEAPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(CWinInetHelperClass *__hidden this, unsigned int *, struct tagHELPER_ATTRIBUTE **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004d60`
- `0x18000c998`
- `0x180012d56`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004dd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004e60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004dd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004e60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004eb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004ec3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004eb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004ec3`

## pseudocode

```c
__int64 __fastcall CWinInetHelperClass::GetAttributes(CWinInetHelperClass *this, unsigned int *a2, LPVOID *a3)
{
  __int128 v5; // xmm6
  unsigned int v6; // ebx
  __int64 v7; // rbx
  struct tagHELPER_ATTRIBUTE *v8; // rax
  _QWORD *v9; // r14
  const unsigned __int16 *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rbp
  unsigned __int16 *v13; // rax
  __int128 v15; // [rsp+20h] [rbp-68h] BYREF
  __int128 v16; // [rsp+30h] [rbp-58h] BYREF

  v5 = *((_OWORD *)this + 302);
  v16 = v5;
  if ( !a2 || !a3 || *a3 || *a2 )
    return (unsigned int)-2147024809;
  v15 = 0;
  if ( !memcmp_0(&v16, &v15, 0x10u) )
  {
    v6 = 0;
LABEL_22:
    *a3 = 0;
    *a2 = 0;
    return v6;
  }
  v7 = 144;
  v8 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(0x90u);
  *a3 = v8;
  if ( v8 )
  {
    do
    {
      LOBYTE(v8->pwszName) = 0;
      v8 = (struct tagHELPER_ATTRIBUTE *)((char *)v8 + 1);
      --v7;
    }
    while ( v7 );
    *((_DWORD *)*a3 + 2) = 11;
    v9 = *a3;
    if ( *a3 )
    {
      v10 = L"rootcauseid";
      v11 = 259;
      do
      {
        if ( !*v10 )
          break;
        ++v10;
        --v11;
      }
      while ( v11 );
      v6 = v11 == 0 ? 0x80070057 : 0;
      v12 = (259 - v11) & -(__int64)(v11 != 0);
      if ( v11 )
      {
        v13 = (unsigned __int16 *)CoTaskMemAlloc(2 * v12 + 2);
        *v9 = v13;
        if ( v13 )
        {
          v6 = StringCchCopyW(v13, v12 + 1, L"rootcauseid");
          if ( (v6 & 0x80000000) == 0 )
          {
            *((_OWORD *)*a3 + 1) = v5;
            *a2 = 1;
            return v6;
          }
        }
        else
        {
          v6 = -2147024882;
        }
      }
    }
    else
    {
      v6 = -2147024809;
    }
    if ( *a3 )
    {
      CoTaskMemFree(*(LPVOID *)*a3);
      CoTaskMemFree(*a3);
      goto LABEL_22;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v6;
}

```

## disassembly

```asm
0x180004d60  mov     rax, rsp
0x180004d63  push    rbx
0x180004d64  push    rbp
0x180004d65  push    rsi
0x180004d66  push    rdi
0x180004d67  push    r14
0x180004d69  push    r15
0x180004d6b  sub     rsp, 58h
0x180004d6f  movaps  xmmword ptr [rax-48h], xmm6
0x180004d73  xor     r15d, r15d
0x180004d76  mov     rdi, r8
0x180004d79  mov     rsi, rdx
0x180004d7c  movups  xmm6, xmmword ptr [rcx+12E0h]
0x180004d83  movaps  xmmword ptr [rax-58h], xmm6
0x180004d87  test    rdx, rdx
0x180004d8a  jz      loc_180004ED7
0x180004d90  test    r8, r8
0x180004d93  jz      loc_180004ED7
0x180004d99  cmp     [r8], r15
0x180004d9c  jnz     loc_180004ED7
0x180004da2  cmp     [rdx], r15d
0x180004da5  jnz     loc_180004ED7
0x180004dab  xorps   xmm0, xmm0
0x180004dae  lea     r8d, [r15+10h]; Size
0x180004db2  lea     rdx, [rax-68h]; Buf2
0x180004db6  lea     rcx, [rax-58h]; Buf1
0x180004dba  movups  xmmword ptr [rax-68h], xmm0
0x180004dbe  call    memcmp_0
0x180004dc3  test    eax, eax
0x180004dc5  jnz     short loc_180004DCF
0x180004dc7  mov     ebx, r15d
0x180004dca  jmp     loc_180004ECF
0x180004dcf  mov     ebx, 90h
0x180004dd4  mov     ecx, ebx; cb
0x180004dd6  call    cs:__imp_CoTaskMemAlloc
0x180004ddd  nop     dword ptr [rax+rax+00h]
0x180004de2  mov     [rdi], rax
0x180004de5  test    rax, rax
0x180004de8  jnz     short loc_180004DF4
0x180004dea  mov     ebx, 8007000Eh
0x180004def  jmp     loc_180004EDC
0x180004df4  mov     [rax], r15b
0x180004df7  inc     rax
0x180004dfa  sub     rbx, 1
0x180004dfe  jnz     short loc_180004DF4
0x180004e00  mov     rax, [rdi]
0x180004e03  mov     dword ptr [rax+8], 0Bh
0x180004e0a  mov     r14, [rdi]
0x180004e0d  test    r14, r14
0x180004e10  jz      loc_180004EA4
0x180004e16  mov     edx, 103h
0x180004e1b  lea     rax, aRootcauseid; "rootcauseid"
0x180004e22  mov     ecx, edx
0x180004e24  cmp     [rax], r15w
0x180004e28  jz      short loc_180004E34
0x180004e2a  add     rax, 2
0x180004e2e  sub     rcx, 1
0x180004e32  jnz     short loc_180004E24
0x180004e34  mov     rax, rcx
0x180004e37  neg     rax
0x180004e3a  mov     rax, rcx
0x180004e3d  sbb     ebx, ebx
0x180004e3f  sub     rdx, rcx
0x180004e42  not     ebx
0x180004e44  and     ebx, 80070057h
0x180004e4a  neg     rax
0x180004e4d  sbb     rbp, rbp
0x180004e50  and     rbp, rdx
0x180004e53  test    rcx, rcx
0x180004e56  jz      short loc_180004EA9
0x180004e58  lea     rcx, ds:2[rbp*2]; cb
0x180004e60  call    cs:__imp_CoTaskMemAlloc
0x180004e67  nop     dword ptr [rax+rax+00h]
0x180004e6c  mov     [r14], rax
0x180004e6f  test    rax, rax
0x180004e72  jnz     short loc_180004E7B
0x180004e74  mov     ebx, 8007000Eh
0x180004e79  jmp     short loc_180004EA9
0x180004e7b  lea     rdx, [rbp+1]; unsigned __int64
0x180004e7f  mov     rcx, rax; unsigned __int16 *
0x180004e82  lea     r8, aRootcauseid; "rootcauseid"
0x180004e89  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004e8e  mov     ebx, eax
0x180004e90  test    eax, eax
0x180004e92  js      short loc_180004EA9
0x180004e94  mov     rax, [rdi]
0x180004e97  movdqu  xmmword ptr [rax+10h], xmm6
0x180004e9c  mov     dword ptr [rsi], 1
0x180004ea2  jmp     short loc_180004EDC
0x180004ea4  mov     ebx, 80070057h
0x180004ea9  mov     rcx, [rdi]
0x180004eac  test    rcx, rcx
0x180004eaf  jz      short loc_180004EDC
0x180004eb1  mov     rcx, [rcx]; pv
0x180004eb4  call    cs:__imp_CoTaskMemFree
0x180004ebb  nop     dword ptr [rax+rax+00h]
0x180004ec0  mov     rcx, [rdi]; pv
0x180004ec3  call    cs:__imp_CoTaskMemFree
0x180004eca  nop     dword ptr [rax+rax+00h]
0x180004ecf  mov     [rdi], r15
0x180004ed2  mov     [rsi], r15d
0x180004ed5  jmp     short loc_180004EDC
0x180004ed7  mov     ebx, 80070057h
0x180004edc  movaps  xmm6, [rsp+88h+var_48]
0x180004ee1  mov     eax, ebx
0x180004ee3  add     rsp, 58h
0x180004ee7  pop     r15
0x180004ee9  pop     r14
0x180004eeb  pop     rdi
0x180004eec  pop     rsi
0x180004eed  pop     rbp
0x180004eee  pop     rbx
0x180004eef  retn
```
