# YReader::ParseCharRef(void)

- ea: `0x100404900`
- end: `0x100404a35`
- name: `?ParseCharRef@YReader@@AEAAXXZ`
- size: `309`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x100404de0`
- `0x100408ba0`

## callees

- `0x100401780`
- `0x100404900`
- `0x100415560`
- `0x100417b70`
- `0x100417c20`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseCharRef(YReader *this)
{
  __int64 v1; // rax
  unsigned int v3; // eax
  struct BlockAlloc::Header *v4; // rbx
  __int64 v5; // rdi
  wchar_t *v6; // rdx
  __int64 v7; // rcx
  struct BlockAlloc::Header *v8; // rax
  __int64 v9; // rcx
  int v10; // eax
  wchar_t *v11[2]; // [rsp+20h] [rbp-18h] BYREF

  v1 = *((_QWORD *)this + 55);
  LODWORD(v11[1]) = 0;
  *((_QWORD *)this + 230) = *(_QWORD *)(v1 + 16);
  v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13));
  v4 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
  v5 = v3;
  v6 = (wchar_t *)*((_QWORD *)v4 + 2);
  if ( *((_DWORD *)v4 + 6) - (int)v6 < v3 )
  {
    v7 = *((_QWORD *)v4 + 1);
    if ( v7 )
    {
      while ( 1 )
      {
        v4 = (struct BlockAlloc::Header *)v7;
        if ( *(_DWORD *)(v7 + 24) - (int)v7 - 32 >= v3 )
          break;
        v7 = *(_QWORD *)(v7 + 8);
        if ( !v7 )
          goto LABEL_5;
      }
      *(_QWORD *)(v7 + 16) = v7 + 32;
    }
    else
    {
LABEL_5:
      _mm_lfence();
      v8 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v3, v4);
      *((_QWORD *)v4 + 1) = v8;
      v4 = v8;
    }
    *((_QWORD *)this + 55) = v4;
    v6 = (wchar_t *)*((_QWORD *)v4 + 2);
  }
  *((_QWORD *)v4 + 2) += v5;
  v9 = *((_QWORD *)this + 13);
  v11[0] = v6;
  (*(void (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v9 + 104LL))(v9, v11);
  if ( *v11[0] == 120 )
    v10 = HexCharEntity2Utf16(v11[0] + 1, LODWORD(v11[1]) - 1, v11[0], (unsigned int *)&v11[1]);
  else
    v10 = CharEntity2Utf16(v11[0], (int)v11[1], v11[0], (unsigned int *)&v11[1]);
  if ( v10 < 0 )
  {
    _mm_lfence();
    MXRRaiseException(v10);
    JUMPOUT(0x100404A34LL);
  }
  *((_OWORD *)this + 102) = *(_OWORD *)v11;
  *((_BYTE *)this + 1784) = 0;
  *((_DWORD *)this + 444) = 5;
}

```

## disassembly

```asm
0x100404900  mov     [rsp+arg_0], rbx
0x100404905  mov     [rsp+arg_8], rbp
0x10040490a  mov     [rsp+arg_10], rsi
0x10040490f  push    rdi
0x100404910  sub     rsp, 30h
0x100404914  mov     rax, [rcx+1B8h]
0x10040491b  mov     rsi, rcx
0x10040491e  mov     dword ptr [rsp+38h+var_18+8], 0
0x100404926  mov     rdx, [rax+10h]
0x10040492a  mov     [rcx+730h], rdx
0x100404931  mov     rcx, [rcx+68h]
0x100404935  mov     rax, [rcx]
0x100404938  mov     rax, [rax+60h]
0x10040493c  call    cs:__guard_dispatch_icall_fptr
0x100404942  mov     rbx, [rsi+1B8h]
0x100404949  mov     edi, eax
0x10040494b  mov     rdx, [rbx+10h]
0x10040494f  mov     ecx, [rbx+18h]
0x100404952  sub     ecx, edx
0x100404954  cmp     ecx, eax
0x100404956  jnb     short loc_10040499F
0x100404958  mov     rcx, [rbx+8]
0x10040495c  test    rcx, rcx
0x10040495f  jz      short loc_100404979
0x100404961  mov     eax, [rcx+18h]
0x100404964  mov     rbx, rcx
0x100404967  sub     eax, ecx
0x100404969  sub     eax, 20h ; ' '
0x10040496c  cmp     eax, edi
0x10040496e  jnb     short loc_1004049E2
0x100404970  mov     rcx, [rcx+8]
0x100404974  test    rcx, rcx
0x100404977  jnz     short loc_100404961
0x100404979  lfence
0x10040497c  mov     r8, rbx; struct BlockAlloc::Header *
0x10040497f  lea     rcx, [rsi+1A0h]; this
0x100404986  mov     edx, edi; unsigned int
0x100404988  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x10040498d  mov     [rbx+8], rax
0x100404991  mov     rbx, rax
0x100404994  mov     [rsi+1B8h], rbx
0x10040499b  mov     rdx, [rbx+10h]
0x10040499f  add     [rbx+10h], rdi
0x1004049a3  mov     rcx, [rsi+68h]
0x1004049a7  mov     [rsp+38h+var_18], rdx
0x1004049ac  lea     rdx, [rsp+38h+var_18]
0x1004049b1  mov     rax, [rcx]
0x1004049b4  mov     rax, [rax+68h]
0x1004049b8  call    cs:__guard_dispatch_icall_fptr
0x1004049be  mov     rax, [rsp+38h+var_18]
0x1004049c3  lea     r9, [rsp+38h+var_18+8]; unsigned int *
0x1004049c8  mov     edx, dword ptr [rsp+38h+var_18+8]; int
0x1004049cc  mov     r8, rax; wchar_t *
0x1004049cf  cmp     word ptr [rax], 78h ; 'x'
0x1004049d3  jnz     short loc_1004049EC
0x1004049d5  dec     edx; int
0x1004049d7  lea     rcx, [rax+2]; wchar_t *
0x1004049db  call    ?HexCharEntity2Utf16@@YAJPEB_WHPEA_WPEAI@Z; HexCharEntity2Utf16(wchar_t const *,int,wchar_t *,uint *)
0x1004049e0  jmp     short loc_1004049F4
0x1004049e2  lea     rax, [rcx+20h]
0x1004049e6  mov     [rcx+10h], rax
0x1004049ea  jmp     short loc_100404994
0x1004049ec  mov     rcx, rax; wchar_t *
0x1004049ef  call    ?CharEntity2Utf16@@YAJPEB_WHPEA_WPEAI@Z; CharEntity2Utf16(wchar_t const *,int,wchar_t *,uint *)
0x1004049f4  test    eax, eax
0x1004049f6  js      short loc_100404A2A
0x1004049f8  movups  xmm0, xmmword ptr [rsp+38h+var_18]
0x1004049fd  mov     rbx, [rsp+38h+arg_0]
0x100404a02  mov     rbp, [rsp+38h+arg_8]
0x100404a07  movups  xmmword ptr [rsi+660h], xmm0
0x100404a0e  mov     byte ptr [rsi+6F8h], 0
0x100404a15  mov     dword ptr [rsi+6F0h], 5
0x100404a1f  mov     rsi, [rsp+38h+arg_10]
0x100404a24  add     rsp, 30h
0x100404a28  pop     rdi
0x100404a29  retn
0x100404a2a  lfence
0x100404a2d  mov     ecx, eax; int
0x100404a2f  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
