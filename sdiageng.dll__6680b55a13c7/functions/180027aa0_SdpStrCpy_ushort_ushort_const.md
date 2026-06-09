# SdpStrCpy(ushort * *,ushort const *)

- ea: `0x180027aa0`
- end: `0x180027b74`
- name: `?SdpStrCpy@@YAJPEAPEAGPEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `26`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000533c`
- `0x18000571c`
- `0x180005d60`
- `0x18000615c`
- `0x1800066f8`
- `0x18000680c`
- `0x180006a90`
- `0x18000e4a8`
- `0x1800101cc`
- `0x1800138d0`
- `0x1800170bc`
- `0x180018a9c`
- `0x18001955c`
- `0x18001c224`
- `0x18001cc2c`
- `0x18001e6c0`
- `0x18001e75c`
- `0x18001e808`
- `0x18001e8b0`
- `0x18001e95c`
- `0x18001ea08`
- `0x18001eaf0`
- `0x18001eb94`
- `0x18001ec38`
- `0x180026bf4`
- `0x1800271ec`

## callees

- `0x1800012a4`
- `0x1800012b0`
- `0x18000551c`
- `0x180026fa0`
- `0x180027aa0`

## pseudocode

```c
__int64 __fastcall SdpStrCpy(unsigned __int16 **a1, const unsigned __int16 *a2)
{
  unsigned int v4; // r8d
  int v5; // r9d
  unsigned int v6; // ebx
  __int64 v7; // rax
  unsigned __int64 v8; // rbp
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdi
  int v11; // eax

  if ( !a1 )
  {
    v4 = 133;
LABEL_3:
    v5 = -2147024809;
    v6 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"SdpStrCpy", v4, v5);
    return v6;
  }
  if ( !a2 )
  {
    v4 = 134;
    goto LABEL_3;
  }
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v8 = v7 + 1;
  v9 = (unsigned __int16 *)operator new[](saturated_mul(v7 + 1, 2u));
  v10 = v9;
  if ( !v9 )
  {
    v6 = -2147024882;
    v4 = 139;
    v5 = -2147024882;
    goto LABEL_4;
  }
  v11 = StringCchCopyW(v9, v8, a2);
  v6 = v11;
  if ( v11 >= 0 )
  {
    *a1 = v10;
  }
  else
  {
    SdpDebugTrace(1u, L"SdpStrCpy", 0x8Eu, v11);
    operator delete(v10);
  }
  return v6;
}

```

## disassembly

```asm
0x180027aa0  push    rbx
0x180027aa2  push    rbp
0x180027aa3  push    rsi
0x180027aa4  push    rdi
0x180027aa5  push    r14
0x180027aa7  sub     rsp, 20h
0x180027aab  xor     r14d, r14d
0x180027aae  mov     rbx, rdx
0x180027ab1  mov     rsi, rcx
0x180027ab4  test    rcx, rcx
0x180027ab7  jnz     short loc_180027ADE
0x180027ab9  mov     r8d, 85h; int
0x180027abf  mov     r9d, 80070057h; int
0x180027ac5  mov     ebx, r9d
0x180027ac8  lea     rdx, aSdpstrcpy; "SdpStrCpy"
0x180027acf  mov     ecx, 1; Level
0x180027ad4  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180027ad9  jmp     loc_180027B67
0x180027ade  test    rbx, rbx
0x180027ae1  jnz     short loc_180027AEB
0x180027ae3  mov     r8d, 86h
0x180027ae9  jmp     short loc_180027ABF
0x180027aeb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180027aef  mov     rax, rcx
0x180027af2  inc     rax
0x180027af5  cmp     [rdx+rax*2], r14w
0x180027afa  jnz     short loc_180027AF2
0x180027afc  lea     rbp, [rax+1]
0x180027b00  mov     eax, 2
0x180027b05  mul     rbp
0x180027b08  cmovb   rax, rcx
0x180027b0c  mov     rcx, rax; unsigned __int64
0x180027b0f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180027b14  mov     rdi, rax
0x180027b17  test    rax, rax
0x180027b1a  jnz     short loc_180027B2C
0x180027b1c  mov     ebx, 8007000Eh
0x180027b21  mov     r8d, 8Bh
0x180027b27  mov     r9d, ebx
0x180027b2a  jmp     short loc_180027AC8
0x180027b2c  mov     r8, rbx; unsigned __int16 *
0x180027b2f  mov     rdx, rbp; unsigned __int64
0x180027b32  mov     rcx, rdi; unsigned __int16 *
0x180027b35  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027b3a  mov     ebx, eax
0x180027b3c  test    eax, eax
0x180027b3e  jns     short loc_180027B64
0x180027b40  mov     r9d, eax; int
0x180027b43  lea     rdx, aSdpstrcpy; "SdpStrCpy"
0x180027b4a  mov     r8d, 8Eh; int
0x180027b50  mov     ecx, 1; Level
0x180027b55  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180027b5a  mov     rcx, rdi; Block
0x180027b5d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027b62  jmp     short loc_180027B67
0x180027b64  mov     [rsi], rdi
0x180027b67  mov     eax, ebx
0x180027b69  add     rsp, 20h
0x180027b6d  pop     r14
0x180027b6f  pop     rdi
0x180027b70  pop     rsi
0x180027b71  pop     rbp
0x180027b72  pop     rbx
0x180027b73  retn
```
