# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180009620`
- end: `0x1800096f7`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `215`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007d40`

## callees

- `0x180008d9c`
- `0x18000926c`
- `0x180009620`

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
0x180009620  mov     [rsp+arg_10], rbx
0x180009625  push    rbp
0x180009626  push    rsi
0x180009627  push    rdi
0x180009628  sub     rsp, 20h
0x18000962c  cmp     qword ptr [rcx+18h], 0
0x180009631  mov     rsi, rdx
0x180009634  mov     edi, [rcx+10h]
0x180009637  mov     rbx, rcx
0x18000963a  mov     ebp, 50h ; 'P'
0x18000963f  jnz     short loc_180009676
0x180009641  test    edi, edi
0x180009643  jz      short loc_180009676
0x180009645  mov     edx, 190h; dwBytes
0x18000964a  lea     ecx, [rbp-48h]; dwFlags
0x18000964d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009652  mov     [rbx+18h], rax
0x180009656  test    rax, rax
0x180009659  jz      short loc_180009676
0x18000965b  mov     dword ptr [rbx+20h], 5
0x180009662  lea     rcx, [rax+190h]
0x180009669  jmp     short loc_180009671
0x18000966b  mov     [rax], bp
0x18000966e  add     rax, rbp
0x180009671  cmp     rax, rcx
0x180009674  jnz     short loc_18000966B
0x180009676  mov     r9, [rbx+18h]
0x18000967a  test    r9, r9
0x18000967d  jz      short loc_1800096E9
0x18000967f  test    edi, edi
0x180009681  jz      short loc_1800096AF
0x180009683  movzx   eax, word ptr [rbx+20h]
0x180009687  mov     rcx, r9
0x18000968a  lea     rdx, [rax+rax*4]
0x18000968e  shl     rdx, 4
0x180009692  add     rdx, r9
0x180009695  cmp     rcx, rdx
0x180009698  jz      short loc_1800096AF
0x18000969a  mov     eax, [rbx+10h]
0x18000969d  cmp     [rcx+4], eax
0x1800096a0  jbe     short loc_1800096AA
0x1800096a2  mov     eax, [rsi+8]
0x1800096a5  cmp     [rcx+8], eax
0x1800096a8  jz      short loc_1800096E9
0x1800096aa  add     rcx, rbp
0x1800096ad  jmp     short loc_180009695
0x1800096af  movzx   eax, word ptr [rbx+22h]
0x1800096b3  xor     edx, edx
0x1800096b5  movzx   ecx, word ptr [rbx+20h]
0x1800096b9  inc     eax
0x1800096bb  div     ecx
0x1800096bd  mov     rax, [rbx+8]
0x1800096c1  mov     r8d, 1
0x1800096c7  mov     [rbx+22h], dx
0x1800096cb  lock xadd [rax], r8d
0x1800096d0  movzx   eax, dx
0x1800096d3  inc     r8d; unsigned int
0x1800096d6  mov     rdx, rsi; struct wil::FailureInfo *
0x1800096d9  lea     rcx, [rax+rax*4]
0x1800096dd  shl     rcx, 4
0x1800096e1  add     rcx, r9; this
0x1800096e4  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800096e9  mov     rbx, [rsp+38h+arg_10]
0x1800096ee  add     rsp, 20h
0x1800096f2  pop     rdi
0x1800096f3  pop     rsi
0x1800096f4  pop     rbp
0x1800096f5  retn
```
