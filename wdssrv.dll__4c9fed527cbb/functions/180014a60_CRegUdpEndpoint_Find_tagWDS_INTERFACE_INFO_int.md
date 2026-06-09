# CRegUdpEndpoint::Find(tagWDS_INTERFACE_INFO *,int)

- ea: `0x180014a60`
- end: `0x180014b98`
- name: `?Find@CRegUdpEndpoint@@QEAAPEAVCUdpEndpoint@@PEAUtagWDS_INTERFACE_INFO@@H@Z`
- size: `312`
- prototype: `struct CUdpEndpoint *(CRegUdpEndpoint *__hidden this, struct tagWDS_INTERFACE_INFO *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180002c24`
- `0x180011bb0`
- `0x180011ce0`

## callees

- `0x180014a60`
- `0x18001c106`
- `0x18001d010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180014b6b`
- `KERNEL32!LeaveCriticalSection` at `0x180014b6b`
- `KERNEL32!EnterCriticalSection` at `0x180014a8d`
- `KERNEL32!EnterCriticalSection` at `0x180014a8d`

## pseudocode

```c
struct CUdpEndpoint *__fastcall CRegUdpEndpoint::Find(CRegUdpEndpoint *this, struct tagWDS_INTERFACE_INFO *a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  void (__fastcall ***v7)(_QWORD); // rdi
  __int64 v8; // rbx
  size_t v9; // rbp
  char *v10; // rdx
  __int64 v11; // rax
  char *v12; // rcx
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int64 v21; // rax
  char v23; // [rsp+20h] [rbp-438h] BYREF
  _BYTE Buf1[16]; // [rsp+30h] [rbp-428h] BYREF
  int v25; // [rsp+40h] [rbp-418h]

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v8 = *((_QWORD *)this + 227);
  if ( v8 )
  {
    v9 = *((unsigned int *)a2 + 4);
    while ( 1 )
    {
      v7 = (void (__fastcall ***)(_QWORD))v8;
      v10 = &v23;
      v8 = *(_QWORD *)(v8 + 2304);
      v11 = 8;
      v12 = (char *)v7 + 988;
      do
      {
        v13 = *(_OWORD *)v12;
        v14 = *((_OWORD *)v12 + 1);
        v12 += 128;
        *(_OWORD *)v10 = v13;
        v15 = *((_OWORD *)v12 - 6);
        *((_OWORD *)v10 + 1) = v14;
        v16 = *((_OWORD *)v12 - 5);
        *((_OWORD *)v10 + 2) = v15;
        v17 = *((_OWORD *)v12 - 4);
        *((_OWORD *)v10 + 3) = v16;
        v18 = *((_OWORD *)v12 - 3);
        *((_OWORD *)v10 + 4) = v17;
        v19 = *((_OWORD *)v12 - 2);
        *((_OWORD *)v10 + 5) = v18;
        v20 = *((_OWORD *)v12 - 1);
        *((_OWORD *)v10 + 6) = v19;
        v10 += 128;
        *((_OWORD *)v10 - 1) = v20;
        --v11;
      }
      while ( v11 );
      v21 = *((_QWORD *)v12 + 2);
      *(_OWORD *)v10 = *(_OWORD *)v12;
      *((_QWORD *)v10 + 2) = v21;
      *((_DWORD *)v10 + 6) = *((_DWORD *)v12 + 6);
      if ( v25 == (_DWORD)v9 && !memcmp_0(Buf1, a2, v9) )
        break;
      v7 = 0;
      if ( !v8 )
        goto LABEL_11;
    }
    if ( a3 )
      (**v7)(v7);
  }
LABEL_11:
  LeaveCriticalSection(v3);
  return (struct CUdpEndpoint *)v7;
}

```

## disassembly

```asm
0x180014a60  mov     [rsp+arg_0], rbx
0x180014a65  mov     [rsp+arg_8], rbp
0x180014a6a  mov     [rsp+arg_10], rsi
0x180014a6f  push    rdi
0x180014a70  push    r14
0x180014a72  push    r15
0x180014a74  sub     rsp, 440h
0x180014a7b  lea     rsi, [rcx+10h]
0x180014a7f  mov     rbx, rcx
0x180014a82  mov     rcx, rsi; lpCriticalSection
0x180014a85  mov     r15d, r8d
0x180014a88  mov     r14, rdx
0x180014a8b  xor     edi, edi
0x180014a8d  call    cs:__imp_EnterCriticalSection
0x180014a94  nop     dword ptr [rax+rax+00h]
0x180014a99  mov     rbx, [rbx+718h]
0x180014aa0  test    rbx, rbx
0x180014aa3  jz      loc_180014B68
0x180014aa9  mov     ebp, [r14+10h]
0x180014aad  mov     rdi, rbx
0x180014ab0  lea     rdx, [rsp+458h+var_438]
0x180014ab5  mov     rbx, [rbx+900h]
0x180014abc  mov     eax, 8
0x180014ac1  lea     rcx, [rdi+3DCh]
0x180014ac8  movups  xmm0, xmmword ptr [rcx]
0x180014acb  movups  xmm1, xmmword ptr [rcx+10h]
0x180014acf  lea     rcx, [rcx+80h]
0x180014ad6  movups  xmmword ptr [rdx], xmm0
0x180014ad9  movups  xmm0, xmmword ptr [rcx-60h]
0x180014add  movups  xmmword ptr [rdx+10h], xmm1
0x180014ae1  movups  xmm1, xmmword ptr [rcx-50h]
0x180014ae5  movups  xmmword ptr [rdx+20h], xmm0
0x180014ae9  movups  xmm0, xmmword ptr [rcx-40h]
0x180014aed  movups  xmmword ptr [rdx+30h], xmm1
0x180014af1  movups  xmm1, xmmword ptr [rcx-30h]
0x180014af5  movups  xmmword ptr [rdx+40h], xmm0
0x180014af9  movups  xmm0, xmmword ptr [rcx-20h]
0x180014afd  movups  xmmword ptr [rdx+50h], xmm1
0x180014b01  movups  xmm1, xmmword ptr [rcx-10h]
0x180014b05  movups  xmmword ptr [rdx+60h], xmm0
0x180014b09  lea     rdx, [rdx+80h]
0x180014b10  movups  xmmword ptr [rdx-10h], xmm1
0x180014b14  sub     rax, 1
0x180014b18  jnz     short loc_180014AC8
0x180014b1a  mov     rax, [rcx+10h]
0x180014b1e  movups  xmm0, xmmword ptr [rcx]
0x180014b21  movups  xmmword ptr [rdx], xmm0
0x180014b24  mov     [rdx+10h], rax
0x180014b28  mov     eax, [rcx+18h]
0x180014b2b  mov     [rdx+18h], eax
0x180014b2e  cmp     [rsp+458h+var_418], ebp
0x180014b32  jnz     short loc_180014B48
0x180014b34  mov     r8, rbp; Size
0x180014b37  lea     rcx, [rsp+458h+Buf1]; Buf1
0x180014b3c  mov     rdx, r14; Buf2
0x180014b3f  call    memcmp_0
0x180014b44  test    eax, eax
0x180014b46  jz      short loc_180014B55
0x180014b48  xor     edi, edi
0x180014b4a  test    rbx, rbx
0x180014b4d  jnz     loc_180014AAD
0x180014b53  jmp     short loc_180014B68
0x180014b55  test    r15d, r15d
0x180014b58  jz      short loc_180014B68
0x180014b5a  mov     rdx, [rdi]
0x180014b5d  mov     rcx, rdi
0x180014b60  mov     rax, [rdx]
0x180014b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b68  mov     rcx, rsi; lpCriticalSection
0x180014b6b  call    cs:__imp_LeaveCriticalSection
0x180014b72  nop     dword ptr [rax+rax+00h]
0x180014b77  lea     r11, [rsp+458h+var_18]
0x180014b7f  mov     rax, rdi
0x180014b82  mov     rbx, [r11+20h]
0x180014b86  mov     rbp, [r11+28h]
0x180014b8a  mov     rsi, [r11+30h]
0x180014b8e  mov     rsp, r11
0x180014b91  pop     r15
0x180014b93  pop     r14
0x180014b95  pop     rdi
0x180014b96  retn
```
