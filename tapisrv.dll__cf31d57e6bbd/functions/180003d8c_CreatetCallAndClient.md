# CreatetCallAndClient

- ea: `0x180003d8c`
- end: `0x180003f4f`
- name: `CreatetCallAndClient`
- size: `451`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, __int64, unsigned int *, _DWORD *)`
- caller_count: `8`
- callee_count: `7`
- tags: ``

## callers

- `0x180008500`
- `0x180009f50`
- `0x180010d40`
- `0x180011f40`
- `0x180012170`
- `0x1800166b0`
- `0x1800171f0`
- `0x1800178f0`

## callees

- `0x180003b0c`
- `0x180003d8c`
- `0x180003f58`
- `0x18000469c`
- `0x18002c8d4`
- `0x18003dc84`
- `0x18003fb7c`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180003e1c`
- `KERNEL32!HeapAlloc` at `0x180003e1c`

## string_xrefs

- `0x180003dc9`: `CreatetCallAndClient: enter, ptLineClient=%p`

## pseudocode

```c
__int64 __fastcall CreatetCallAndClient(_QWORD *a1, _QWORD *a2, __int64 a3, unsigned int *a4, _DWORD *a5)
{
  unsigned int v7; // edi
  void *v8; // rsi
  _QWORD *v9; // rcx
  SIZE_T v10; // r15
  void *v11; // rax
  _DWORD *v13; // rdi
  unsigned int v14; // r14d
  int v15; // [rsp+30h] [rbp-68h]
  _DWORD *v16; // [rsp+58h] [rbp-40h] BYREF
  _QWORD *v20; // [rsp+C8h] [rbp+30h]

  v7 = 0;
  v8 = 0;
  v16 = 0;
  TRACELogPrint(524290, "CreatetCallAndClient: enter, ptLineClient=%p", a1);
  v9 = (_QWORD *)a1[4];
  v20 = v9;
  v10 = *(unsigned int *)(a1[2] + 64LL);
  if ( *(_DWORD *)a1 == 1229734732 )
  {
    v11 = HeapAlloc(ghTapisrvHeap, 8u, v10);
    v8 = v11;
    if ( v11 )
      memcpy_0(v11, *(const void **)(a1[2] + 72LL), v10);
    else
      v7 = -2147483580;
    v9 = v20;
  }
  else
  {
    v7 = -2147483605;
  }
  if ( v7 )
    return v7;
  v7 = CreatetCall(v9, 0, 0, (const void **)&v16, a4, a5, v15);
  if ( v7 )
  {
    ServerFree(v8);
    return v7;
  }
  v13 = v16;
  v14 = CreatetCallClient((_DWORD)v16, (_DWORD)a1, 4, 0, 0, a3, 0);
  if ( v14 )
  {
    ServerFree(v8);
    v13[8] = 1;
    DestroytCall(v13);
    *a2 = 0;
    *a5 = 0;
    return v14;
  }
  else
  {
    v13[19] = v10;
    *((_QWORD *)v13 + 10) = v8;
    *a2 = v13;
    return 0;
  }
}

```

## disassembly

```asm
0x180003d8c  mov     rax, rsp
0x180003d8f  mov     [rax+20h], r9
0x180003d93  mov     [rax+18h], r8
0x180003d97  mov     [rax+10h], rdx
0x180003d9b  mov     [rax+8], rcx
0x180003d9f  push    rsi
0x180003da0  push    rdi
0x180003da1  push    r12
0x180003da3  push    r13
0x180003da5  push    r14
0x180003da7  push    r15
0x180003da9  sub     rsp, 68h
0x180003dad  mov     r12, rdx
0x180003db0  mov     r14, rcx
0x180003db3  xor     edi, edi
0x180003db5  mov     [rax-54h], edi
0x180003db8  xor     esi, esi
0x180003dba  mov     [rax-50h], rsi
0x180003dbe  mov     [rax-40h], rsi
0x180003dc2  mov     [rax-48h], rsi
0x180003dc6  mov     r8, rcx
0x180003dc9  lea     rdx, aCreatetcalland; "CreatetCallAndClient: enter, ptLineClie"...
0x180003dd0  mov     ecx, 80002h
0x180003dd5  call    TRACELogPrint
0x180003dda  nop
0x180003ddb  mov     rcx, [r14+20h]
0x180003ddf  mov     [rsp+98h+arg_28], rcx
0x180003de7  mov     [rsp+98h+var_48], rcx
0x180003dec  mov     rax, [r14+10h]
0x180003df0  mov     r15d, [rax+40h]
0x180003df4  mov     [rsp+98h+var_54], r15d
0x180003df9  cmp     dword ptr [r14], 494C434Ch
0x180003e00  jz      short loc_180003E0D
0x180003e02  mov     edi, 8000002Bh
0x180003e07  mov     [rsp+98h+var_58], edi
0x180003e0b  jmp     short loc_180003E55
0x180003e0d  mov     r8, r15; dwBytes
0x180003e10  mov     edx, 8; dwFlags
0x180003e15  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180003e1c  call    cs:__imp_HeapAlloc
0x180003e22  mov     rsi, rax
0x180003e25  mov     [rsp+98h+lpMem], rax
0x180003e2a  test    rax, rax
0x180003e2d  jz      short loc_180003E44
0x180003e2f  mov     rdx, [r14+10h]
0x180003e33  mov     r8, r15; Size
0x180003e36  mov     rdx, [rdx+48h]; Src
0x180003e3a  mov     rcx, rax; void *
0x180003e3d  call    memcpy_0
0x180003e42  jmp     short loc_180003E4D
0x180003e44  mov     edi, 80000044h
0x180003e49  mov     [rsp+98h+var_58], edi
0x180003e4d  mov     rcx, [rsp+98h+arg_28]
0x180003e55  jmp     short loc_180003E87
0x180003e57  mov     rsi, [rsp+98h+lpMem]
0x180003e5c  mov     rcx, rsi; lpMem
0x180003e5f  call    ServerFree
0x180003e64  mov     edi, 8000002Bh
0x180003e69  mov     [rsp+98h+var_58], edi
0x180003e6d  mov     r12, [rsp+98h+arg_8]
0x180003e75  mov     r14, [rsp+98h+arg_0]
0x180003e7d  mov     r15d, [rsp+98h+var_54]
0x180003e82  mov     rcx, [rsp+98h+var_48]
0x180003e87  test    edi, edi
0x180003e89  jz      short loc_180003E92
0x180003e8b  mov     eax, edi
0x180003e8d  jmp     loc_180003F40
0x180003e92  mov     r13, [rsp+98h+arg_20]
0x180003e9a  mov     [rsp+98h+var_70], r13
0x180003e9f  mov     rax, [rsp+98h+arg_18]
0x180003ea7  mov     [rsp+98h+var_78], rax
0x180003eac  lea     r9, [rsp+98h+var_40]
0x180003eb1  xor     r8d, r8d
0x180003eb4  xor     edx, edx
0x180003eb6  call    CreatetCall
0x180003ebb  mov     edi, eax
0x180003ebd  test    eax, eax
0x180003ebf  jz      short loc_180003ECB
0x180003ec1  mov     rcx, rsi; lpMem
0x180003ec4  call    ServerFree
0x180003ec9  jmp     short loc_180003E8B
0x180003ecb  mov     [rsp+98h+var_68], 0
0x180003ed3  mov     rax, [rsp+98h+arg_10]
0x180003edb  mov     [rsp+98h+var_70], rax
0x180003ee0  mov     dword ptr [rsp+98h+var_78], 0
0x180003ee8  xor     r9d, r9d
0x180003eeb  lea     r8d, [r9+4]
0x180003eef  mov     rdx, r14
0x180003ef2  mov     rdi, [rsp+98h+var_40]
0x180003ef7  mov     rcx, rdi
0x180003efa  call    CreatetCallClient
0x180003eff  mov     r14d, eax
0x180003f02  test    eax, eax
0x180003f04  jz      short loc_180003F32
0x180003f06  mov     rcx, rsi; lpMem
0x180003f09  call    ServerFree
0x180003f0e  mov     dword ptr [rdi+20h], 1
0x180003f15  mov     rcx, rdi
0x180003f18  call    DestroytCall
0x180003f1d  mov     qword ptr [r12], 0
0x180003f25  mov     dword ptr [r13+0], 0
0x180003f2d  mov     eax, r14d
0x180003f30  jmp     short loc_180003F40
0x180003f32  mov     [rdi+4Ch], r15d
0x180003f36  mov     [rdi+50h], rsi
0x180003f3a  mov     [r12], rdi
0x180003f3e  xor     eax, eax
0x180003f40  add     rsp, 68h
0x180003f44  pop     r15
0x180003f46  pop     r14
0x180003f48  pop     r13
0x180003f4a  pop     r12
0x180003f4c  pop     rdi
0x180003f4d  pop     rsi
0x180003f4e  retn
```
