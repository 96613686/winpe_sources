# DllGetClassObject

- ea: `0x180082b30`
- end: `0x180082c26`
- name: `DllGetClassObject`
- size: `246`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001260`
- `0x180082b30`
- `0x1800c6084`
- `0x1800c60f0`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int v7; // ebx
  const void **v8; // rsi
  _QWORD *v9; // rax

  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  if ( memcmp(riid, &qword_1800CB130, 0x10u) && memcmp(riid, &qword_1800CB140, 0x10u) )
    return -2147467262;
  v7 = 0;
  while ( 1 )
  {
    v8 = (const void **)((char *)&off_18010C940 + 16 * v7);
    if ( !memcmp(*v8, rclsid, 0x10u) )
      break;
    if ( ++v7 >= 1 )
      return -2147221231;
  }
  v9 = (_QWORD *)sub_180001260(24);
  if ( v9 )
  {
    _InterlockedIncrement(&dword_18011B848);
    v9[1] = v8;
    *v9 = off_1800C9878;
    *((_DWORD *)v9 + 4) = 0;
    *ppv = v9;
    (*(void (__fastcall **)(_QWORD *))(*v9 + 8LL))(v9);
    return 0;
  }
  else
  {
    *ppv = 0;
    return -2147024882;
  }
}

```

## disassembly

```asm
0x180082b30  push    rbx
0x180082b32  push    rbp
0x180082b33  push    rsi
0x180082b34  push    rdi
0x180082b35  push    r15
0x180082b37  sub     rsp, 20h
0x180082b3b  mov     rdi, r8
0x180082b3e  mov     rbx, rdx
0x180082b41  mov     rbp, rcx
0x180082b44  test    r8, r8
0x180082b47  jnz     short loc_180082B53
0x180082b49  mov     eax, 80004003h
0x180082b4e  jmp     loc_180082C1A
0x180082b53  mov     qword ptr [r8], 0
0x180082b5a  lea     rdx, qword_1800CB130; Buf2
0x180082b61  mov     r15d, 10h
0x180082b67  mov     rcx, rbx; Buf1
0x180082b6a  mov     r8d, r15d; Size
0x180082b6d  call    memcmp
0x180082b72  test    eax, eax
0x180082b74  jz      short loc_180082B96
0x180082b76  mov     r8d, r15d; Size
0x180082b79  lea     rdx, qword_1800CB140; Buf2
0x180082b80  mov     rcx, rbx; Buf1
0x180082b83  call    memcmp
0x180082b88  test    eax, eax
0x180082b8a  jz      short loc_180082B96
0x180082b8c  mov     eax, 80004002h
0x180082b91  jmp     loc_180082C1A
0x180082b96  xor     ebx, ebx
0x180082b98  lea     rcx, off_18010C940
0x180082b9f  movsxd  rsi, ebx
0x180082ba2  shl     rsi, 4
0x180082ba6  mov     r8, r15; Size
0x180082ba9  add     rsi, rcx
0x180082bac  mov     rdx, rbp; Buf2
0x180082baf  mov     rcx, [rsi]; Buf1
0x180082bb2  call    memcmp
0x180082bb7  test    eax, eax
0x180082bb9  jz      short loc_180082BC9
0x180082bbb  inc     ebx
0x180082bbd  cmp     ebx, 1
0x180082bc0  jl      short loc_180082B98
0x180082bc2  mov     eax, 80040111h
0x180082bc7  jmp     short loc_180082C1A
0x180082bc9  mov     ecx, 18h
0x180082bce  call    sub_180001260
0x180082bd3  mov     rdx, rax
0x180082bd6  test    rax, rax
0x180082bd9  jz      short loc_180082C0E
0x180082bdb  lock inc cs:dword_18011B848
0x180082be2  mov     [rdx+8], rsi
0x180082be6  lea     rax, off_1800C9878
0x180082bed  mov     [rdx], rax
0x180082bf0  mov     dword ptr [rdx+10h], 0
0x180082bf7  mov     [rdi], rdx
0x180082bfa  mov     rcx, [rdx]
0x180082bfd  mov     rax, [rcx+8]
0x180082c01  mov     rcx, rdx
0x180082c04  call    cs:__guard_dispatch_icall_fptr
0x180082c0a  xor     eax, eax
0x180082c0c  jmp     short loc_180082C1A
0x180082c0e  mov     qword ptr [rdi], 0
0x180082c15  mov     eax, 8007000Eh
0x180082c1a  add     rsp, 20h
0x180082c1e  pop     r15
0x180082c20  pop     rdi
0x180082c21  pop     rsi
0x180082c22  pop     rbp
0x180082c23  pop     rbx
0x180082c24  retn
```
