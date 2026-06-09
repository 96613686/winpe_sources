# CJob::GetCurFile(ushort * *)

- ea: `0x180025840`
- end: `0x180025916`
- name: `?GetCurFile@CJob@@UEAAJPEAPEAG@Z`
- size: `214`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800040c0`
- `0x180025840`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800258bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800258bf`

## pseudocode

```c
__int64 __fastcall CJob::GetCurFile(CJob *this, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rbx
  unsigned int v4; // edi
  __int64 v5; // rax
  unsigned __int64 v6; // r14
  unsigned __int16 *v7; // rax
  __int64 result; // rax
  unsigned __int16 *v9; // r10
  unsigned __int16 v10[8]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v11; // [rsp+30h] [rbp-38h]

  v2 = (unsigned __int16 *)*((_QWORD *)this + 18);
  *(_OWORD *)v10 = 0;
  v11 = 0;
  if ( v2 && *v2 )
  {
    v4 = 0;
  }
  else
  {
    StringCchCopyW(v10, 0x10u, L"*.job");
    v2 = v10;
    v4 = 1;
  }
  v5 = -1;
  do
    ++v5;
  while ( v2[v5] );
  v6 = (int)v5 + 1LL;
  v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6);
  if ( v7 )
  {
    *v7 = 0;
    StringCchCopyW(v7, v6, v2);
    result = v4;
    *a2 = v9;
  }
  else
  {
    *a2 = 0;
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180025840  mov     [rsp+arg_10], rbx
0x180025845  mov     [rsp+arg_18], rbp
0x18002584a  push    rsi
0x18002584b  push    rdi
0x18002584c  push    r14
0x18002584e  sub     rsp, 50h
0x180025852  mov     rax, cs:__security_cookie
0x180025859  xor     rax, rsp
0x18002585c  mov     [rsp+68h+var_28], rax
0x180025861  mov     rbx, [rcx+90h]
0x180025868  xorps   xmm0, xmm0
0x18002586b  xor     ebp, ebp
0x18002586d  mov     rsi, rdx
0x180025870  movups  xmmword ptr [rsp+68h+var_48], xmm0
0x180025875  movups  [rsp+68h+var_38], xmm0
0x18002587a  test    rbx, rbx
0x18002587d  jz      short loc_180025888
0x18002587f  cmp     [rbx], bp
0x180025882  jz      short loc_180025888
0x180025884  mov     edi, ebp
0x180025886  jmp     short loc_1800258A8
0x180025888  lea     r8, aJob_2; "*.job"
0x18002588f  mov     edx, 10h; unsigned __int64
0x180025894  lea     rcx, [rsp+68h+var_48]; unsigned __int16 *
0x180025899  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002589e  lea     rbx, [rsp+68h+var_48]
0x1800258a3  mov     edi, 1
0x1800258a8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800258ac  inc     rax
0x1800258af  cmp     [rbx+rax*2], bp
0x1800258b3  jnz     short loc_1800258AC
0x1800258b5  movsxd  r14, eax
0x1800258b8  inc     r14
0x1800258bb  lea     rcx, [r14+r14]; cb
0x1800258bf  call    cs:__imp_CoTaskMemAlloc
0x1800258c6  nop     dword ptr [rax+rax+00h]
0x1800258cb  mov     r10, rax
0x1800258ce  test    rax, rax
0x1800258d1  jnz     short loc_1800258DD
0x1800258d3  mov     [rsi], rbp
0x1800258d6  mov     eax, 8007000Eh
0x1800258db  jmp     short loc_1800258F3
0x1800258dd  mov     r8, rbx; unsigned __int16 *
0x1800258e0  mov     [rax], bp
0x1800258e3  mov     rdx, r14; unsigned __int64
0x1800258e6  mov     rcx, r10; unsigned __int16 *
0x1800258e9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800258ee  mov     eax, edi
0x1800258f0  mov     [rsi], r10
0x1800258f3  mov     rcx, [rsp+68h+var_28]
0x1800258f8  xor     rcx, rsp; StackCookie
0x1800258fb  call    __security_check_cookie
0x180025900  lea     r11, [rsp+68h+var_18]
0x180025905  mov     rbx, [r11+30h]
0x180025909  mov     rbp, [r11+38h]
0x18002590d  mov     rsp, r11
0x180025910  pop     r14
0x180025912  pop     rdi
0x180025913  pop     rsi
0x180025914  retn
```
