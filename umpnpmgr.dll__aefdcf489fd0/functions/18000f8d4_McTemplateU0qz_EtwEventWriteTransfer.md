# McTemplateU0qz_EtwEventWriteTransfer

- ea: `0x18000f8d4`
- end: `0x18000f96a`
- name: `McTemplateU0qz_EtwEventWriteTransfer`
- size: `150`
- prototype: `__int64 __fastcall(__int64, __int64, int, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009d70`

## callees

- `0x18000f8d4`
- `0x18000f970`
- `0x180018970`

## pseudocode

```c
__int64 __fastcall McTemplateU0qz_EtwEventWriteTransfer(__int64 a1, __int64 a2, int a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // eax
  _BYTE v7[16]; // [rsp+30h] [rbp-48h] BYREF
  int *v8; // [rsp+40h] [rbp-38h]
  __int64 v9; // [rsp+48h] [rbp-30h]
  const wchar_t *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]
  int v13; // [rsp+90h] [rbp+18h] BYREF

  v13 = a3;
  v9 = 4;
  v8 = &v13;
  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  v11 = v5;
  v12 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v10 = a4;
  return McGenEventWrite_EtwEventWriteTransfer(
           (unsigned int)L"NULL",
           (unsigned int)WORKER_THREAD_START,
           a3,
           3,
           (__int64)v7);
}

```

## disassembly

```asm
0x18000f8d4  mov     r11, rsp
0x18000f8d7  mov     [r11+18h], r8d
0x18000f8db  sub     rsp, 78h
0x18000f8df  mov     rax, cs:__security_cookie
0x18000f8e6  xor     rax, rsp
0x18000f8e9  mov     [rsp+78h+var_18], rax
0x18000f8ee  xor     edx, edx
0x18000f8f0  mov     qword ptr [r11-30h], 4
0x18000f8f8  lea     rax, [r11+18h]
0x18000f8fc  mov     [r11-38h], rax
0x18000f900  test    r9, r9
0x18000f903  jz      short loc_18000F91C
0x18000f905  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f909  inc     rax
0x18000f90c  cmp     [r9+rax*2], dx
0x18000f911  jnz     short loc_18000F909
0x18000f913  lea     eax, ds:2[rax*2]
0x18000f91a  jmp     short loc_18000F921
0x18000f91c  mov     eax, 0Ah
0x18000f921  test    r9, r9
0x18000f924  mov     [rsp+78h+var_20], eax
0x18000f928  lea     rcx, aNull; "NULL"
0x18000f92f  mov     [rsp+78h+var_1C], edx
0x18000f933  cmovz   r9, rcx
0x18000f937  lea     rax, [rsp+78h+var_48]
0x18000f93c  mov     [rsp+78h+var_28], r9
0x18000f941  lea     rdx, WORKER_THREAD_START
0x18000f948  mov     r9d, 3
0x18000f94e  mov     [rsp+78h+var_58], rax
0x18000f953  call    McGenEventWrite_EtwEventWriteTransfer
0x18000f958  mov     rcx, [rsp+78h+var_18]
0x18000f95d  xor     rcx, rsp; StackCookie
0x18000f960  call    __security_check_cookie
0x18000f965  add     rsp, 78h
0x18000f969  retn
```
