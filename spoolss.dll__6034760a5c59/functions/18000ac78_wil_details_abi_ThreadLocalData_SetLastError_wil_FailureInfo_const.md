# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000ac78`
- end: `0x18000ad47`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008320`

## callees

- `0x1800096c8`
- `0x18000a8e0`
- `0x18000ac78`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v3; // edi
  _WORD *v5; // rax
  _WORD *v6; // rcx
  __int64 v7; // r9
  __int64 i; // rcx
  unsigned __int16 v9; // dx
  volatile signed __int32 *v10; // rax

  v3 = *((_DWORD *)this + 4);
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v3 )
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
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    if ( v3 )
    {
      for ( i = *((_QWORD *)this + 3); i != v7 + 80LL * *((unsigned __int16 *)this + 16); i += 80 )
      {
        if ( *(_DWORD *)(i + 4) > *((_DWORD *)this + 4) && *(_DWORD *)(i + 8) == *((_DWORD *)a2 + 2) )
          return;
      }
    }
    v9 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
    v10 = (volatile signed __int32 *)*((_QWORD *)this + 1);
    *((_WORD *)this + 17) = v9;
    wil::details_abi::ThreadLocalFailureInfo::Set(
      (wil::details_abi::ThreadLocalFailureInfo *)(v7 + 80LL * v9),
      a2,
      _InterlockedIncrement(v10));
  }
}

```

## disassembly

```asm
0x18000ac78  push    rbx
0x18000ac7a  push    rbp
0x18000ac7b  push    rsi
0x18000ac7c  push    rdi
0x18000ac7d  sub     rsp, 28h
0x18000ac81  cmp     qword ptr [rcx+18h], 0
0x18000ac86  mov     rsi, rdx
0x18000ac89  mov     edi, [rcx+10h]
0x18000ac8c  mov     rbx, rcx
0x18000ac8f  mov     ebp, 50h ; 'P'
0x18000ac94  jnz     short loc_18000ACCB
0x18000ac96  test    edi, edi
0x18000ac98  jz      short loc_18000ACCB
0x18000ac9a  mov     edx, 190h; dwBytes
0x18000ac9f  lea     ecx, [rbp-48h]; dwFlags
0x18000aca2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000aca7  mov     [rbx+18h], rax
0x18000acab  test    rax, rax
0x18000acae  jz      short loc_18000ACCB
0x18000acb0  mov     dword ptr [rbx+20h], 5
0x18000acb7  lea     rcx, [rax+190h]
0x18000acbe  jmp     short loc_18000ACC6
0x18000acc0  mov     [rax], bp
0x18000acc3  add     rax, rbp
0x18000acc6  cmp     rax, rcx
0x18000acc9  jnz     short loc_18000ACC0
0x18000accb  mov     r9, [rbx+18h]
0x18000accf  test    r9, r9
0x18000acd2  jz      short loc_18000AD3E
0x18000acd4  test    edi, edi
0x18000acd6  jz      short loc_18000AD04
0x18000acd8  movzx   eax, word ptr [rbx+20h]
0x18000acdc  mov     rcx, r9
0x18000acdf  lea     rdx, [rax+rax*4]
0x18000ace3  shl     rdx, 4
0x18000ace7  add     rdx, r9
0x18000acea  cmp     rcx, rdx
0x18000aced  jz      short loc_18000AD04
0x18000acef  mov     eax, [rbx+10h]
0x18000acf2  cmp     [rcx+4], eax
0x18000acf5  jbe     short loc_18000ACFF
0x18000acf7  mov     eax, [rsi+8]
0x18000acfa  cmp     [rcx+8], eax
0x18000acfd  jz      short loc_18000AD3E
0x18000acff  add     rcx, rbp
0x18000ad02  jmp     short loc_18000ACEA
0x18000ad04  movzx   eax, word ptr [rbx+22h]
0x18000ad08  xor     edx, edx
0x18000ad0a  movzx   ecx, word ptr [rbx+20h]
0x18000ad0e  inc     eax
0x18000ad10  div     ecx
0x18000ad12  mov     rax, [rbx+8]
0x18000ad16  mov     r8d, 1
0x18000ad1c  mov     [rbx+22h], dx
0x18000ad20  lock xadd [rax], r8d
0x18000ad25  movzx   eax, dx
0x18000ad28  inc     r8d; unsigned int
0x18000ad2b  mov     rdx, rsi; struct wil::FailureInfo *
0x18000ad2e  lea     rcx, [rax+rax*4]
0x18000ad32  shl     rcx, 4
0x18000ad36  add     rcx, r9; this
0x18000ad39  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000ad3e  add     rsp, 28h
0x18000ad42  pop     rdi
0x18000ad43  pop     rsi
0x18000ad44  pop     rbp
0x18000ad45  pop     rbx
0x18000ad46  retn
```
