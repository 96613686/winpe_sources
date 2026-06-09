# YReader::SetTokenData3(wchar_t,StringPtr *)

- ea: `0x100401ab0`
- end: `0x100401bb3`
- name: `?SetTokenData3@YReader@@AEAAX_WPEAUStringPtr@@@Z`
- size: `259`
- prototype: `void __fastcall(YReader *__hidden this, wchar_t, struct StringPtr *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1004058d0`
- `0x100405a00`
- `0x1004069e0`
- `0x100407100`

## callees

- `0x100401780`
- `0x100401ab0`
- `0x100415490`
- `0x100415560`

## pseudocode

```c
void __fastcall YReader::SetTokenData3(YReader *this, __int16 a2, struct StringPtr *a3)
{
  char *v5; // rdx
  BlockAlloc *v7; // rcx
  struct BlockAlloc::Header *v8; // rbx
  _WORD *v9; // r8
  __int64 v10; // rax
  struct BlockAlloc::Header *v11; // rax
  unsigned int v12; // r8d
  char *v13; // rax
  __int64 v14; // rcx

  v5 = *(char **)a3;
  if ( *(_QWORD *)a3 )
  {
    v12 = *((_DWORD *)a3 + 2);
    if ( v12 > 0x3FFFFFFD )
    {
      MXRRaiseException(-2147024882);
      JUMPOUT(0x100401BB2LL);
    }
    v13 = BlockAlloc::ReallocData((YReader *)((char *)this + 416), v5, 2 * v12 + 2);
    v14 = *((unsigned int *)a3 + 2);
    *(_QWORD *)a3 = v13;
    *(_WORD *)&v13[2 * v14] = a2;
    ++*((_DWORD *)a3 + 2);
  }
  else
  {
    v7 = (YReader *)((char *)this + 416);
    v8 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
    v9 = (_WORD *)*((_QWORD *)v8 + 2);
    if ( (unsigned int)(*((_DWORD *)v8 + 6) - (_DWORD)v9) < 2 )
    {
      v10 = *((_QWORD *)v8 + 1);
      if ( v10 )
      {
        while ( 1 )
        {
          v8 = (struct BlockAlloc::Header *)v10;
          if ( (unsigned int)(*(_DWORD *)(v10 + 24) - v10 - 32) >= 2 )
            break;
          v10 = *(_QWORD *)(v10 + 8);
          if ( !v10 )
            goto LABEL_6;
        }
        *(_QWORD *)(v10 + 16) = v10 + 32;
      }
      else
      {
LABEL_6:
        v11 = BlockAlloc::EnqueueBlock(v7, 2, v8);
        *((_QWORD *)v8 + 1) = v11;
        v8 = v11;
      }
      *((_QWORD *)this + 55) = v8;
      v9 = (_WORD *)*((_QWORD *)v8 + 2);
    }
    *((_QWORD *)v8 + 2) += 2LL;
    *(_QWORD *)a3 = v9;
    *v9 = a2;
    *((_DWORD *)a3 + 2) = 1;
  }
}

```

## disassembly

```asm
0x100401ab0  mov     [rsp+arg_8], rbp
0x100401ab5  mov     [rsp+arg_10], rsi
0x100401aba  push    rdi
0x100401abb  sub     rsp, 20h
0x100401abf  movzx   ebp, dx
0x100401ac2  mov     rdi, r8
0x100401ac5  mov     rdx, [r8]; void *
0x100401ac8  mov     rsi, rcx
0x100401acb  test    rdx, rdx
0x100401ace  jnz     loc_100401B6A
0x100401ad4  mov     [rsp+28h+arg_0], rbx
0x100401ad9  add     rcx, 1A0h; this
0x100401ae0  mov     rbx, [rsi+1B8h]
0x100401ae7  mov     r8, [rbx+10h]
0x100401aeb  mov     eax, [rbx+18h]
0x100401aee  sub     eax, r8d
0x100401af1  cmp     eax, 2
0x100401af4  jnb     short loc_100401B38
0x100401af6  mov     rax, [rbx+8]
0x100401afa  test    rax, rax
0x100401afd  jz      short loc_100401B19
0x100401aff  nop
0x100401b00  mov     rbx, rax
0x100401b03  mov     eax, [rax+18h]
0x100401b06  sub     eax, ebx
0x100401b08  sub     eax, 20h ; ' '
0x100401b0b  cmp     eax, 2
0x100401b0e  jnb     short loc_100401B60
0x100401b10  mov     rax, [rbx+8]
0x100401b14  test    rax, rax
0x100401b17  jnz     short loc_100401B00
0x100401b19  mov     r8, rbx; struct BlockAlloc::Header *
0x100401b1c  mov     edx, 2; unsigned int
0x100401b21  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x100401b26  mov     [rbx+8], rax
0x100401b2a  mov     rbx, rax
0x100401b2d  mov     [rsi+1B8h], rbx
0x100401b34  mov     r8, [rbx+10h]
0x100401b38  add     qword ptr [rbx+10h], 2
0x100401b3d  mov     rbx, [rsp+28h+arg_0]
0x100401b42  mov     [rdi], r8
0x100401b45  mov     [r8], bp
0x100401b49  mov     dword ptr [rdi+8], 1
0x100401b50  mov     rbp, [rsp+28h+arg_8]
0x100401b55  mov     rsi, [rsp+28h+arg_10]
0x100401b5a  add     rsp, 20h
0x100401b5e  pop     rdi
0x100401b5f  retn
0x100401b60  lea     rax, [rbx+20h]
0x100401b64  mov     [rbx+10h], rax
0x100401b68  jmp     short loc_100401B2D
0x100401b6a  mov     r8d, [r8+8]
0x100401b6e  cmp     r8d, 3FFFFFFDh
0x100401b75  ja      short loc_100401BA8
0x100401b77  lea     r8d, ds:2[r8*2]; unsigned int
0x100401b7f  add     rcx, 1A0h; this
0x100401b86  call    ?ReallocData@BlockAlloc@@QEAAPEAXPEAXK@Z; BlockAlloc::ReallocData(void *,ulong)
0x100401b8b  mov     ecx, [rdi+8]
0x100401b8e  mov     rsi, [rsp+28h+arg_10]
0x100401b93  mov     [rdi], rax
0x100401b96  mov     [rax+rcx*2], bp
0x100401b9a  inc     dword ptr [rdi+8]
0x100401b9d  mov     rbp, [rsp+28h+arg_8]
0x100401ba2  add     rsp, 20h
0x100401ba6  pop     rdi
0x100401ba7  retn
0x100401ba8  mov     ecx, 8007000Eh; int
0x100401bad  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
