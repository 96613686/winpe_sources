# CUwfStaticConfiguration::get_StaticVolumeConfiguration(ulong,CUwfStaticVolumeConfiguration * *)

- ea: `0x18000b5c0`
- end: `0x18000b69c`
- name: `?get_StaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAJKPEAPEAVCUwfStaticVolumeConfiguration@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *__hidden this, unsigned int, struct CUwfStaticVolumeConfiguration **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180001390`
- `0x180008300`
- `0x18000b5c0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::get_StaticVolumeConfiguration(
        CUwfStaticConfiguration *this,
        unsigned int a2,
        struct CUwfStaticVolumeConfiguration **a3)
{
  unsigned int v6; // edi
  struct CUwfStaticVolumeConfiguration *v7; // rbx
  char *v8; // rax
  struct CUwfStaticVolumeConfiguration *v9; // rax

  if ( a3 )
  {
    v7 = (struct CUwfStaticVolumeConfiguration *)*((_QWORD *)this + 5);
    if ( v7 )
    {
      v9 = 0;
      v6 = 0;
    }
    else
    {
      v8 = (char *)operator new(0x28u);
      v7 = (struct CUwfStaticVolumeConfiguration *)v8;
      if ( !v8 )
        return (unsigned int)-2147024882;
      *(_WORD *)(v8 + 9) = 1;
      *(_QWORD *)v8 = &CUwfStaticVolumeConfiguration::`vftable';
      *((_DWORD *)v8 + 3) = -1;
      *((_QWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 3) = 0;
      *((_QWORD *)v8 + 4) = 0;
      v6 = CUwfStaticVolumeConfiguration::Initialize(
             (CUwfStaticVolumeConfiguration *)v8,
             *((HKEY *)this + 3),
             a2,
             *((_BYTE *)this + 8),
             *((struct CUwfConfiguration **)this + 4),
             this);
      if ( (v6 & 0x80000000) != 0 )
      {
LABEL_12:
        (**(void (__fastcall ***)(struct CUwfStaticVolumeConfiguration *, __int64))v7)(v7, 1);
        return v6;
      }
      *((_QWORD *)this + 5) = v7;
      v9 = v7;
    }
    if ( *((_DWORD *)v7 + 3) == a2 )
    {
      *a3 = v7;
      return v6;
    }
    v7 = v9;
    v6 = -2147024891;
    if ( !v9 )
      return v6;
    goto LABEL_12;
  }
  return (unsigned int)-2147467261;
}

```

## disassembly

```asm
0x18000b5c0  push    rbx
0x18000b5c2  push    rbp
0x18000b5c3  push    rsi
0x18000b5c4  push    rdi
0x18000b5c5  push    r14
0x18000b5c7  sub     rsp, 30h
0x18000b5cb  mov     r14, r8
0x18000b5ce  mov     ebp, edx
0x18000b5d0  mov     rsi, rcx
0x18000b5d3  test    r8, r8
0x18000b5d6  jnz     short loc_18000B5E2
0x18000b5d8  mov     edi, 80004003h
0x18000b5dd  jmp     loc_18000B68F
0x18000b5e2  mov     rbx, [rcx+28h]
0x18000b5e6  test    rbx, rbx
0x18000b5e9  jnz     short loc_18000B661
0x18000b5eb  lea     ecx, [rbx+28h]; Size
0x18000b5ee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b5f3  mov     rbx, rax
0x18000b5f6  test    rax, rax
0x18000b5f9  jz      short loc_18000B65A
0x18000b5fb  mov     word ptr [rbx+9], 1
0x18000b601  lea     rax, ??_7CUwfStaticVolumeConfiguration@@6B@; const CUwfStaticVolumeConfiguration::`vftable'
0x18000b608  mov     [rbx], rax
0x18000b60b  mov     r8d, ebp; unsigned int
0x18000b60e  mov     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x18000b615  mov     rcx, rbx; this
0x18000b618  mov     qword ptr [rbx+10h], 0
0x18000b620  mov     qword ptr [rbx+18h], 0
0x18000b628  mov     qword ptr [rbx+20h], 0
0x18000b630  mov     rax, [rsi+20h]
0x18000b634  mov     r9b, [rsi+8]; bool
0x18000b638  mov     rdx, [rsi+18h]; HKEY
0x18000b63c  mov     [rsp+58h+var_30], rsi; struct CUwfStaticConfiguration *
0x18000b641  mov     [rsp+58h+var_38], rax; struct CUwfConfiguration *
0x18000b646  call    ?Initialize@CUwfStaticVolumeConfiguration@@QEAAJPEAUHKEY__@@K_NPEAVCUwfConfiguration@@PEAVCUwfStaticConfiguration@@@Z; CUwfStaticVolumeConfiguration::Initialize(HKEY__ *,ulong,bool,CUwfConfiguration *,CUwfStaticConfiguration *)
0x18000b64b  mov     edi, eax
0x18000b64d  test    eax, eax
0x18000b64f  js      short loc_18000B67C
0x18000b651  mov     [rsi+28h], rbx
0x18000b655  mov     rax, rbx
0x18000b658  jmp     short loc_18000B665
0x18000b65a  mov     edi, 8007000Eh
0x18000b65f  jmp     short loc_18000B68F
0x18000b661  xor     eax, eax
0x18000b663  xor     edi, edi
0x18000b665  cmp     [rbx+0Ch], ebp
0x18000b668  jnz     short loc_18000B66F
0x18000b66a  mov     [r14], rbx
0x18000b66d  jmp     short loc_18000B68F
0x18000b66f  mov     rbx, rax
0x18000b672  mov     edi, 80070005h
0x18000b677  test    rax, rax
0x18000b67a  jz      short loc_18000B68F
0x18000b67c  mov     rax, [rbx]
0x18000b67f  mov     edx, 1
0x18000b684  mov     rcx, rbx
0x18000b687  mov     rax, [rax]
0x18000b68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b68f  mov     eax, edi
0x18000b691  add     rsp, 30h
0x18000b695  pop     r14
0x18000b697  pop     rdi
0x18000b698  pop     rsi
0x18000b699  pop     rbp
0x18000b69a  pop     rbx
0x18000b69b  retn
```
