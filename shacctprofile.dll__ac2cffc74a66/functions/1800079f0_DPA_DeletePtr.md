# DPA_DeletePtr

- ea: `0x1800079f0`
- end: `0x180007aaa`
- name: `DPA_DeletePtr`
- size: `186`
- prototype: `PVOID __stdcall(HDPA hdpa, int i)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006180`

## callees

- `0x1800078fc`
- `0x1800079f0`
- `0x18000973c`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
PVOID __stdcall DPA_DeletePtr(HDPA hdpa, int i)
{
  int v3; // r8d
  __int64 v4; // r9
  void **v5; // rcx
  void *v6; // rdi
  void *v7; // r8
  unsigned __int64 v8; // rax
  void *v9; // rcx
  __int64 v11; // [rsp+40h] [rbp+8h] BYREF

  if ( !hdpa )
    return 0;
  if ( i < 0 )
    return 0;
  v3 = *(_DWORD *)hdpa;
  if ( i >= *(_DWORD *)hdpa )
    return 0;
  v4 = *((_QWORD *)hdpa + 1);
  v5 = (void **)(v4 + 8LL * i);
  v6 = *v5;
  if ( i < v3 - 1 )
    memmove_0(v5, (const void *)(v4 + 8LL * (i + 1)), 8LL * (v3 - i - 1));
  --*(_DWORD *)hdpa;
  if ( *((_DWORD *)hdpa + 6) - *(_DWORD *)hdpa > *((_DWORD *)hdpa + 7) )
  {
    v7 = (void *)*((_QWORD *)hdpa + 1);
    v8 = *((_DWORD *)hdpa + 6) - *((_DWORD *)hdpa + 7);
    v9 = (void *)*((_QWORD *)hdpa + 2);
    v11 = 0;
    if ( (int)CCv6s_HeapReallocArray<void *>(v9, *(__int64 *)&i, v7, v4, v8, &v11) >= 0 )
      *((_QWORD *)hdpa + 1) = v11;
    *((_DWORD *)hdpa + 6) -= *((_DWORD *)hdpa + 7);
  }
  return v6;
}

```

## disassembly

```asm
0x1800079f0  mov     [rsp+arg_8], rbx
0x1800079f5  push    rdi
0x1800079f6  sub     rsp, 30h
0x1800079fa  mov     rbx, rcx
0x1800079fd  test    rcx, rcx
0x180007a00  jz      loc_180007A9D
0x180007a06  test    edx, edx
0x180007a08  js      loc_180007A9D
0x180007a0e  mov     r8d, [rcx]
0x180007a11  cmp     edx, r8d
0x180007a14  jge     loc_180007A9D
0x180007a1a  mov     r9, [rcx+8]
0x180007a1e  movsxd  rax, edx
0x180007a21  lea     rcx, [r9+rax*8]; void *
0x180007a25  mov     rdi, [rcx]
0x180007a28  lea     eax, [r8-1]
0x180007a2c  cmp     edx, eax
0x180007a2e  jge     short loc_180007A4C
0x180007a30  sub     r8d, edx
0x180007a33  lea     eax, [rdx+1]
0x180007a36  dec     r8d
0x180007a39  movsxd  rdx, eax
0x180007a3c  movsxd  r8, r8d
0x180007a3f  shl     r8, 3; Size
0x180007a43  lea     rdx, [r9+rdx*8]; Src
0x180007a47  call    memmove_0
0x180007a4c  dec     dword ptr [rbx]
0x180007a4e  mov     ecx, [rbx+18h]
0x180007a51  mov     eax, ecx
0x180007a53  sub     eax, [rbx]
0x180007a55  cmp     eax, [rbx+1Ch]
0x180007a58  jle     short loc_180007A98
0x180007a5a  sub     ecx, [rbx+1Ch]
0x180007a5d  mov     r8, [rbx+8]
0x180007a61  movsxd  rax, ecx
0x180007a64  lea     rcx, [rsp+38h+arg_0]
0x180007a69  mov     [rsp+38h+var_10], rcx
0x180007a6e  mov     rcx, [rbx+10h]
0x180007a72  mov     [rsp+38h+arg_0], 0
0x180007a7b  mov     [rsp+38h+var_18], rax
0x180007a80  call    ??$CCv6s_HeapReallocArray@PEAX@@YAJPEAXK0_K1PEAPEAPEAX@Z; CCv6s_HeapReallocArray<void *>(void *,ulong,void *,unsigned __int64,unsigned __int64,void * * *)
0x180007a85  test    eax, eax
0x180007a87  js      short loc_180007A92
0x180007a89  mov     rcx, [rsp+38h+arg_0]
0x180007a8e  mov     [rbx+8], rcx
0x180007a92  mov     ecx, [rbx+1Ch]
0x180007a95  sub     [rbx+18h], ecx
0x180007a98  mov     rax, rdi
0x180007a9b  jmp     short loc_180007A9F
0x180007a9d  xor     eax, eax
0x180007a9f  mov     rbx, [rsp+38h+arg_8]
0x180007aa4  add     rsp, 30h
0x180007aa8  pop     rdi
0x180007aa9  retn
```
