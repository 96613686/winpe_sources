# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000bd00`
- end: `0x18000bf55`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `597`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800099c0`

## callees

- `0x180008f7c`
- `0x180008ffc`
- `0x18000ace0`
- `0x18000bd00`
- `0x18000c836`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000bec9`
- `KERNEL32!HeapFree` at `0x18000bec9`
- `KERNEL32!GetProcessHeap` at `0x18000beb5`
- `KERNEL32!GetProcessHeap` at `0x18000beb5`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v2; // edi
  _WORD *v5; // rax
  _WORD *v6; // rcx
  _DWORD *v7; // r9
  _DWORD *v8; // rcx
  _DWORD *v9; // rdx
  __int64 v10; // r8
  unsigned __int16 v11; // dx
  _DWORD *v12; // rdi
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // r9
  __int64 v18; // rcx
  _QWORD *v19; // rsi
  __int64 v20; // rcx
  __int64 v21; // rdx
  unsigned __int64 v22; // rbp
  LPVOID v23; // r15
  void *v24; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v26; // rcx
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rax
  void *v30; // rax

  v2 = *((_DWORD *)this + 4);
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v2 )
    {
      v5 = wil::details::ProcessHeapAlloc(8u, 0x190u);
      *((_QWORD *)this + 3) = v5;
      if ( v5 )
      {
        *((_DWORD *)this + 8) = 5;
        v6 = v5 + 200;
        while ( v5 != v6 )
        {
          *v5 = 80;
          v5 += 40;
        }
      }
    }
  }
  v7 = (_DWORD *)*((_QWORD *)this + 3);
  if ( !v7 )
    return;
  if ( !v2 || (v8 = &v7[20 * *((unsigned __int16 *)this + 16)], v7 == v8) )
  {
LABEL_14:
    v10 = 1;
    v11 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
    *((_WORD *)this + 17) = v11;
    v12 = &v7[20 * v11];
    v13 = -1;
    v12[1] = _InterlockedIncrement(*((volatile signed __int32 **)this + 1));
    v12[2] = *((_DWORD *)a2 + 2);
    *((_QWORD *)v12 + 2) = 0;
    *((_WORD *)v12 + 12) = *((_WORD *)a2 + 32);
    *((_BYTE *)v12 + 26) = *(_BYTE *)a2;
    *((_QWORD *)v12 + 4) = 0;
    *((_QWORD *)v12 + 5) = *((_QWORD *)a2 + 17);
    *((_QWORD *)v12 + 6) = *((_QWORD *)a2 + 18);
    *((_QWORD *)v12 + 7) = 0;
    v14 = *((_QWORD *)a2 + 7);
    if ( v14 )
    {
      v16 = -1;
      do
        ++v16;
      while ( *(_BYTE *)(v14 + v16) );
      v15 = v16 + 1;
    }
    else
    {
      v15 = 1;
    }
    v17 = *((_QWORD *)a2 + 16);
    if ( v17 )
    {
      v18 = -1;
      do
        ++v18;
      while ( *(_BYTE *)(v17 + v18) );
      v10 = v18 + 1;
    }
    v19 = (_QWORD *)((char *)a2 + 24);
    v20 = *((_QWORD *)a2 + 3);
    if ( v20 )
    {
      do
        ++v13;
      while ( *(_WORD *)(v20 + 2 * v13) );
      v21 = 2 * v13 + 2;
    }
    else
    {
      v21 = 2;
    }
    v22 = v15 + v21 + v10;
    if ( *((_QWORD *)v12 + 8) )
    {
      if ( *((_QWORD *)v12 + 9) >= v22 )
      {
LABEL_32:
        v26 = *((_QWORD *)v12 + 8);
        if ( v26 )
        {
          v27 = v26 + *((_QWORD *)v12 + 9);
          v28 = wil::details::WriteResultString<char const *>(v26, v27, *((_QWORD *)a2 + 7), v12 + 4);
          v29 = wil::details::WriteResultString<char const *>(v28, v27, *((_QWORD *)a2 + 16), v12 + 8);
          v30 = (void *)wil::details::WriteResultString<unsigned short const *>(v29, v27, *v19, v12 + 14);
          memset_0(v30, 0, v27 - (_QWORD)v30);
        }
        return;
      }
      v19 = (_QWORD *)((char *)a2 + 24);
    }
    v23 = wil::details::ProcessHeapAlloc(8u, v15 + v21 + v10);
    if ( v23 )
    {
      v24 = (void *)*((_QWORD *)v12 + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v24);
      *((_QWORD *)v12 + 8) = v23;
      *((_QWORD *)v12 + 9) = v22;
    }
    goto LABEL_32;
  }
  v9 = v7 + 2;
  while ( *(v9 - 1) <= *((_DWORD *)this + 4) || *v9 != *((_DWORD *)a2 + 2) )
  {
    v9 += 20;
    if ( v9 - 2 == v8 )
      goto LABEL_14;
  }
}

```

## disassembly

```asm
0x18000bd00  mov     rax, rsp
0x18000bd03  mov     [rax+8], rbx
0x18000bd07  mov     [rax+10h], rbp
0x18000bd0b  mov     [rax+18h], rsi
0x18000bd0f  mov     [rax+20h], rdi
0x18000bd13  push    r12
0x18000bd15  push    r14
0x18000bd17  push    r15
0x18000bd19  sub     rsp, 20h
0x18000bd1d  mov     edi, [rcx+10h]
0x18000bd20  mov     esi, 50h ; 'P'
0x18000bd25  xor     r12d, r12d
0x18000bd28  mov     r14, rdx
0x18000bd2b  mov     rbx, rcx
0x18000bd2e  lea     r15d, [rsi-48h]
0x18000bd32  cmp     [rcx+18h], r12
0x18000bd36  jnz     short loc_18000BD6D
0x18000bd38  test    edi, edi
0x18000bd3a  jz      short loc_18000BD6D
0x18000bd3c  mov     edx, 190h; dwBytes
0x18000bd41  mov     ecx, r15d; dwFlags
0x18000bd44  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000bd49  mov     [rbx+18h], rax
0x18000bd4d  test    rax, rax
0x18000bd50  jz      short loc_18000BD6D
0x18000bd52  mov     dword ptr [rbx+20h], 5
0x18000bd59  lea     rcx, [rax+190h]
0x18000bd60  jmp     short loc_18000BD68
0x18000bd62  mov     [rax], si
0x18000bd65  add     rax, rsi
0x18000bd68  cmp     rax, rcx
0x18000bd6b  jnz     short loc_18000BD62
0x18000bd6d  mov     r9, [rbx+18h]
0x18000bd71  test    r9, r9
0x18000bd74  jz      loc_18000BF35
0x18000bd7a  test    edi, edi
0x18000bd7c  jz      short loc_18000BDB8
0x18000bd7e  movzx   eax, word ptr [rbx+20h]
0x18000bd82  lea     rcx, [rax+rax*4]
0x18000bd86  shl     rcx, 4
0x18000bd8a  add     rcx, r9
0x18000bd8d  cmp     r9, rcx
0x18000bd90  jz      short loc_18000BDB8
0x18000bd92  mov     r8d, [rbx+10h]
0x18000bd96  lea     rdx, [r9+8]
0x18000bd9a  cmp     [rdx-4], r8d
0x18000bd9e  jbe     short loc_18000BDAC
0x18000bda0  mov     eax, [r14+8]
0x18000bda4  cmp     [rdx], eax
0x18000bda6  jz      loc_18000BF35
0x18000bdac  add     rdx, rsi
0x18000bdaf  lea     rax, [rdx-8]
0x18000bdb3  cmp     rax, rcx
0x18000bdb6  jnz     short loc_18000BD9A
0x18000bdb8  movzx   eax, word ptr [rbx+22h]
0x18000bdbc  mov     r8d, 1
0x18000bdc2  movzx   ecx, word ptr [rbx+20h]
0x18000bdc6  add     eax, r8d
0x18000bdc9  xor     edx, edx
0x18000bdcb  div     ecx
0x18000bdcd  mov     ecx, r8d
0x18000bdd0  movzx   eax, dx
0x18000bdd3  mov     [rbx+22h], dx
0x18000bdd7  lea     rdi, [rax+rax*4]
0x18000bddb  mov     rax, [rbx+8]
0x18000bddf  shl     rdi, 4
0x18000bde3  add     rdi, r9
0x18000bde6  lock xadd [rax], ecx
0x18000bdea  add     ecx, r8d
0x18000bded  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000bdf1  mov     [rdi+4], ecx
0x18000bdf4  mov     eax, [r14+8]
0x18000bdf8  mov     [rdi+8], eax
0x18000bdfb  mov     [rdi+10h], r12
0x18000bdff  movzx   eax, word ptr [r14+40h]
0x18000be04  mov     [rdi+18h], ax
0x18000be08  mov     al, [r14]
0x18000be0b  mov     [rdi+1Ah], al
0x18000be0e  mov     [rdi+20h], r12
0x18000be12  mov     rax, [r14+88h]
0x18000be19  mov     [rdi+28h], rax
0x18000be1d  mov     rax, [r14+90h]
0x18000be24  mov     [rdi+30h], rax
0x18000be28  mov     [rdi+38h], r12
0x18000be2c  mov     rcx, [r14+38h]
0x18000be30  test    rcx, rcx
0x18000be33  jnz     short loc_18000BE3A
0x18000be35  mov     eax, r8d
0x18000be38  jmp     short loc_18000BE49
0x18000be3a  mov     rax, rdx
0x18000be3d  inc     rax
0x18000be40  cmp     [rcx+rax], r12b
0x18000be44  jnz     short loc_18000BE3D
0x18000be46  add     rax, r8
0x18000be49  mov     r9, [r14+80h]
0x18000be50  test    r9, r9
0x18000be53  jz      short loc_18000BE64
0x18000be55  mov     rcx, rdx
0x18000be58  inc     rcx
0x18000be5b  cmp     [r9+rcx], r12b
0x18000be5f  jnz     short loc_18000BE58
0x18000be61  add     r8, rcx; unsigned __int64
0x18000be64  lea     rsi, [r14+18h]
0x18000be68  mov     rcx, [rsi]
0x18000be6b  test    rcx, rcx
0x18000be6e  jnz     short loc_18000BE75
0x18000be70  lea     edx, [rcx+2]
0x18000be73  jmp     short loc_18000BE87
0x18000be75  inc     rdx
0x18000be78  cmp     [rcx+rdx*2], r12w
0x18000be7d  jnz     short loc_18000BE75
0x18000be7f  lea     rdx, ds:2[rdx*2]
0x18000be87  lea     rbp, [rdx+r8]
0x18000be8b  add     rbp, rax
0x18000be8e  cmp     [rdi+40h], r12
0x18000be92  jz      short loc_18000BE9E
0x18000be94  cmp     [rdi+48h], rbp
0x18000be98  jnb     short loc_18000BEDD
0x18000be9a  lea     rsi, [r14+18h]
0x18000be9e  mov     rdx, rbp; dwBytes
0x18000bea1  mov     ecx, r15d; dwFlags
0x18000bea4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000bea9  mov     r15, rax
0x18000beac  test    rax, rax
0x18000beaf  jz      short loc_18000BEDD
0x18000beb1  mov     rbx, [rdi+40h]
0x18000beb5  call    cs:__imp_GetProcessHeap
0x18000bebc  nop     dword ptr [rax+rax+00h]
0x18000bec1  mov     r8, rbx; lpMem
0x18000bec4  xor     edx, edx; dwFlags
0x18000bec6  mov     rcx, rax; hHeap
0x18000bec9  call    cs:__imp_HeapFree
0x18000bed0  nop     dword ptr [rax+rax+00h]
0x18000bed5  mov     [rdi+40h], r15
0x18000bed9  mov     [rdi+48h], rbp
0x18000bedd  mov     rcx, [rdi+40h]
0x18000bee1  test    rcx, rcx
0x18000bee4  jz      short loc_18000BF35
0x18000bee6  mov     rbx, [rdi+48h]
0x18000beea  lea     r9, [rdi+10h]
0x18000beee  mov     r8, [r14+38h]
0x18000bef2  add     rbx, rcx
0x18000bef5  mov     rdx, rbx
0x18000bef8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000befd  mov     r8, [r14+80h]
0x18000bf04  lea     r9, [rdi+20h]
0x18000bf08  mov     rdx, rbx
0x18000bf0b  mov     rcx, rax
0x18000bf0e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000bf13  mov     r8, [rsi]
0x18000bf16  lea     r9, [rdi+38h]
0x18000bf1a  mov     rdx, rbx
0x18000bf1d  mov     rcx, rax
0x18000bf20  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000bf25  sub     rbx, rax
0x18000bf28  xor     edx, edx; Val
0x18000bf2a  mov     r8, rbx; Size
0x18000bf2d  mov     rcx, rax; void *
0x18000bf30  call    memset_0
0x18000bf35  mov     rbx, [rsp+38h+arg_0]
0x18000bf3a  mov     rbp, [rsp+38h+arg_8]
0x18000bf3f  mov     rsi, [rsp+38h+arg_10]
0x18000bf44  mov     rdi, [rsp+38h+arg_18]
0x18000bf49  add     rsp, 20h
0x18000bf4d  pop     r15
0x18000bf4f  pop     r14
0x18000bf51  pop     r12
0x18000bf53  retn
```
