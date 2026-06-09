# DllGetClassObject

- ea: `0x180082ad0`
- end: `0x180082bc6`
- name: `DllGetClassObject`
- size: `246`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001260`
- `0x180082ad0`
- `0x1800c6024`
- `0x1800c6090`

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
0x180082ad0  push    rbx
0x180082ad2  push    rbp
0x180082ad3  push    rsi
0x180082ad4  push    rdi
0x180082ad5  push    r15
0x180082ad7  sub     rsp, 20h
0x180082adb  mov     rdi, r8
0x180082ade  mov     rbx, rdx
0x180082ae1  mov     rbp, rcx
0x180082ae4  test    r8, r8
0x180082ae7  jnz     short loc_180082AF3
0x180082ae9  mov     eax, 80004003h
0x180082aee  jmp     loc_180082BBA
0x180082af3  mov     qword ptr [r8], 0
0x180082afa  lea     rdx, qword_1800CB130; Buf2
0x180082b01  mov     r15d, 10h
0x180082b07  mov     rcx, rbx; Buf1
0x180082b0a  mov     r8d, r15d; Size
0x180082b0d  call    memcmp
0x180082b12  test    eax, eax
0x180082b14  jz      short loc_180082B36
0x180082b16  mov     r8d, r15d; Size
0x180082b19  lea     rdx, qword_1800CB140; Buf2
0x180082b20  mov     rcx, rbx; Buf1
0x180082b23  call    memcmp
0x180082b28  test    eax, eax
0x180082b2a  jz      short loc_180082B36
0x180082b2c  mov     eax, 80004002h
0x180082b31  jmp     loc_180082BBA
0x180082b36  xor     ebx, ebx
0x180082b38  lea     rcx, off_18010C940
0x180082b3f  movsxd  rsi, ebx
0x180082b42  shl     rsi, 4
0x180082b46  mov     r8, r15; Size
0x180082b49  add     rsi, rcx
0x180082b4c  mov     rdx, rbp; Buf2
0x180082b4f  mov     rcx, [rsi]; Buf1
0x180082b52  call    memcmp
0x180082b57  test    eax, eax
0x180082b59  jz      short loc_180082B69
0x180082b5b  inc     ebx
0x180082b5d  cmp     ebx, 1
0x180082b60  jl      short loc_180082B38
0x180082b62  mov     eax, 80040111h
0x180082b67  jmp     short loc_180082BBA
0x180082b69  mov     ecx, 18h
0x180082b6e  call    sub_180001260
0x180082b73  mov     rdx, rax
0x180082b76  test    rax, rax
0x180082b79  jz      short loc_180082BAE
0x180082b7b  lock inc cs:dword_18011B848
0x180082b82  mov     [rdx+8], rsi
0x180082b86  lea     rax, off_1800C9878
0x180082b8d  mov     [rdx], rax
0x180082b90  mov     dword ptr [rdx+10h], 0
0x180082b97  mov     [rdi], rdx
0x180082b9a  mov     rcx, [rdx]
0x180082b9d  mov     rax, [rcx+8]
0x180082ba1  mov     rcx, rdx
0x180082ba4  call    cs:__guard_dispatch_icall_fptr
0x180082baa  xor     eax, eax
0x180082bac  jmp     short loc_180082BBA
0x180082bae  mov     qword ptr [rdi], 0
0x180082bb5  mov     eax, 8007000Eh
0x180082bba  add     rsp, 20h
0x180082bbe  pop     r15
0x180082bc0  pop     rdi
0x180082bc1  pop     rsi
0x180082bc2  pop     rbp
0x180082bc3  pop     rbx
0x180082bc4  retn
```
