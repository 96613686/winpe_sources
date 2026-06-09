# CMRCICompression::CompressFile(ushort const *,ushort const *,ulong,CMRCICompression::CompressionLevel,CMRCIControl *)

- ea: `0x1800354b0`
- end: `0x180035565`
- name: `?CompressFile@CMRCICompression@@QEAAHPEBG0KW4CompressionLevel@1@PEAVCMRCIControl@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, const wchar_t *, unsigned int, int, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800354b0`
- `0x180035570`

## import_xrefs

- `msvcrt!_wunlink` at `0x18003554c`
- `msvcrt!_wunlink` at `0x18003554c`
- `msvcrt!_close` at `0x18003552c`
- `msvcrt!_close` at `0x180035539`
- `msvcrt!_close` at `0x18003552c`
- `msvcrt!_close` at `0x180035539`
- `msvcrt!_wopen` at `0x1800354d8`
- `msvcrt!_wopen` at `0x1800354ee`
- `msvcrt!_wopen` at `0x1800354d8`
- `msvcrt!_wopen` at `0x1800354ee`

## pseudocode

```c
__int64 __fastcall CMRCICompression::CompressFile(
        __int64 a1,
        const wchar_t *a2,
        const wchar_t *a3,
        unsigned int a4,
        int a5,
        _DWORD *a6)
{
  unsigned int v9; // edi
  unsigned int v10; // ebp
  unsigned int v11; // eax
  int v12; // ebx

  v9 = 0;
  v10 = _wopen(a2, 0x8000, 0);
  v11 = _wopen(a3, 33537, 384);
  v12 = v11;
  if ( v10 != -1 )
  {
    if ( v11 != -1 )
      v9 = CMRCICompression::CompressFileV1(a1, v10, v11, a4, a5, a6);
    _close(v10);
  }
  if ( v12 != -1 )
    _close(v12);
  if ( a6 && *a6 )
  {
    _wunlink(a3);
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x1800354b0  push    rbx
0x1800354b2  push    rbp
0x1800354b3  push    rsi
0x1800354b4  push    rdi
0x1800354b5  push    r12
0x1800354b7  push    r14
0x1800354b9  push    r15
0x1800354bb  sub     rsp, 30h
0x1800354bf  mov     rax, rdx
0x1800354c2  mov     r14, r8
0x1800354c5  mov     r12, rcx
0x1800354c8  xor     r8d, r8d
0x1800354cb  mov     rcx, rax; FileName
0x1800354ce  mov     edx, 8000h; OpenFlag
0x1800354d3  mov     r15d, r9d
0x1800354d6  xor     edi, edi
0x1800354d8  call    cs:__imp__wopen
0x1800354de  mov     edx, 8301h; OpenFlag
0x1800354e3  mov     r8d, 180h
0x1800354e9  mov     rcx, r14; FileName
0x1800354ec  mov     ebp, eax
0x1800354ee  call    cs:__imp__wopen
0x1800354f4  mov     rsi, [rsp+68h+arg_28]
0x1800354fc  mov     ebx, eax
0x1800354fe  cmp     ebp, 0FFFFFFFFh
0x180035501  jz      short loc_180035532
0x180035503  cmp     eax, 0FFFFFFFFh
0x180035506  jz      short loc_18003552A
0x180035508  mov     eax, [rsp+68h+arg_20]
0x18003550f  mov     r9d, r15d
0x180035512  mov     [rsp+68h+var_40], rsi
0x180035517  mov     r8d, ebx
0x18003551a  mov     edx, ebp
0x18003551c  mov     [rsp+68h+var_48], eax
0x180035520  mov     rcx, r12
0x180035523  call    ?CompressFileV1@CMRCICompression@@IEAAHHHKW4CompressionLevel@1@PEAVCMRCIControl@@@Z; CMRCICompression::CompressFileV1(int,int,ulong,CMRCICompression::CompressionLevel,CMRCIControl *)
0x180035528  mov     edi, eax
0x18003552a  mov     ecx, ebp; FileHandle
0x18003552c  call    cs:__imp__close
0x180035532  cmp     ebx, 0FFFFFFFFh
0x180035535  jz      short loc_18003553F
0x180035537  mov     ecx, ebx; FileHandle
0x180035539  call    cs:__imp__close
0x18003553f  test    rsi, rsi
0x180035542  jz      short loc_180035554
0x180035544  cmp     dword ptr [rsi], 0
0x180035547  jz      short loc_180035554
0x180035549  mov     rcx, r14; FileName
0x18003554c  call    cs:__imp__wunlink
0x180035552  xor     edi, edi
0x180035554  mov     eax, edi
0x180035556  add     rsp, 30h
0x18003555a  pop     r15
0x18003555c  pop     r14
0x18003555e  pop     r12
0x180035560  pop     rdi
0x180035561  pop     rsi
0x180035562  pop     rbp
0x180035563  pop     rbx
0x180035564  retn
```
