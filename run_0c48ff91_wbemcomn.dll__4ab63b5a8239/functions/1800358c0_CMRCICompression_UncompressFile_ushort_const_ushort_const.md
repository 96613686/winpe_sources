# CMRCICompression::UncompressFile(ushort const *,ushort const *)

- ea: `0x1800358c0`
- end: `0x18003596a`
- name: `?UncompressFile@CMRCICompression@@QEAAHPEBG0@Z`
- size: `170`
- prototype: `__int64 __fastcall(CMRCICompression *__hidden this, wchar_t *FileName, wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800358c0`
- `0x180035970`

## import_xrefs

- `msvcrt!_lseek` at `0x180035929`
- `msvcrt!_lseek` at `0x180035929`
- `msvcrt!_close` at `0x18003594c`
- `msvcrt!_close` at `0x180035959`
- `msvcrt!_close` at `0x18003594c`
- `msvcrt!_close` at `0x180035959`
- `msvcrt!_read` at `0x180035917`
- `msvcrt!_read` at `0x180035917`
- `msvcrt!_wopen` at `0x1800358df`
- `msvcrt!_wopen` at `0x1800358f5`
- `msvcrt!_wopen` at `0x1800358df`
- `msvcrt!_wopen` at `0x1800358f5`

## pseudocode

```c
__int64 __fastcall CMRCICompression::UncompressFile(CMRCICompression *this, wchar_t *FileName, wchar_t *a3)
{
  unsigned int v5; // esi
  int v6; // edi
  int v7; // eax
  int v8; // ebx
  char DstBuf; // [rsp+68h] [rbp+20h] BYREF

  v5 = 0;
  v6 = _wopen(FileName, 0x8000, 0);
  v7 = _wopen(a3, 33537, 384);
  v8 = v7;
  if ( v6 != -1 )
  {
    if ( v7 != -1 )
    {
      DstBuf = 0;
      if ( _read(v6, &DstBuf, 1u) == 1 && _lseek(v6, 0, 0) != -1 && DstBuf == 1 )
        v5 = CMRCICompression::UncompressFileV1(this, v6, v8);
    }
    _close(v6);
  }
  if ( v8 != -1 )
    _close(v8);
  return v5;
}

```

## disassembly

```asm
0x1800358c0  push    rbx
0x1800358c2  push    rbp
0x1800358c3  push    rsi
0x1800358c4  push    rdi
0x1800358c5  sub     rsp, 28h
0x1800358c9  mov     rax, rdx
0x1800358cc  mov     rbx, r8
0x1800358cf  mov     rbp, rcx
0x1800358d2  xor     r8d, r8d
0x1800358d5  mov     rcx, rax; FileName
0x1800358d8  mov     edx, 8000h; OpenFlag
0x1800358dd  xor     esi, esi
0x1800358df  call    cs:__imp__wopen
0x1800358e5  mov     edx, 8301h; OpenFlag
0x1800358ea  mov     r8d, 180h
0x1800358f0  mov     rcx, rbx; FileName
0x1800358f3  mov     edi, eax
0x1800358f5  call    cs:__imp__wopen
0x1800358fb  mov     ebx, eax
0x1800358fd  cmp     edi, 0FFFFFFFFh
0x180035900  jz      short loc_180035952
0x180035902  cmp     eax, 0FFFFFFFFh
0x180035905  jz      short loc_18003594A
0x180035907  lea     r8d, [rsi+1]; MaxCharCount
0x18003590b  mov     [rsp+48h+DstBuf], sil
0x180035910  lea     rdx, [rsp+48h+DstBuf]; DstBuf
0x180035915  mov     ecx, edi; FileHandle
0x180035917  call    cs:__imp__read
0x18003591d  cmp     eax, 1
0x180035920  jnz     short loc_18003594A
0x180035922  xor     r8d, r8d; Origin
0x180035925  xor     edx, edx; Offset
0x180035927  mov     ecx, edi; FileHandle
0x180035929  call    cs:__imp__lseek
0x18003592f  cmp     eax, 0FFFFFFFFh
0x180035932  jz      short loc_18003594A
0x180035934  cmp     [rsp+48h+DstBuf], 1
0x180035939  jnz     short loc_18003594A
0x18003593b  mov     r8d, ebx; int
0x18003593e  mov     edx, edi; int
0x180035940  mov     rcx, rbp; this
0x180035943  call    ?UncompressFileV1@CMRCICompression@@IEAAHHH@Z; CMRCICompression::UncompressFileV1(int,int)
0x180035948  mov     esi, eax
0x18003594a  mov     ecx, edi; FileHandle
0x18003594c  call    cs:__imp__close
0x180035952  cmp     ebx, 0FFFFFFFFh
0x180035955  jz      short loc_18003595F
0x180035957  mov     ecx, ebx; FileHandle
0x180035959  call    cs:__imp__close
0x18003595f  mov     eax, esi
0x180035961  add     rsp, 28h
0x180035965  pop     rdi
0x180035966  pop     rsi
0x180035967  pop     rbp
0x180035968  pop     rbx
0x180035969  retn
```
