# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180006238`
- end: `0x18000630e`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `214`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004540`

## callees

- `0x180005c00`
- `0x180005ea0`
- `0x180006238`

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
0x180006238  mov     [rsp+arg_10], rbx
0x18000623d  push    rbp
0x18000623e  push    rsi
0x18000623f  push    rdi
0x180006240  sub     rsp, 20h
0x180006244  cmp     qword ptr [rcx+18h], 0
0x180006249  mov     rsi, rdx
0x18000624c  mov     edi, [rcx+10h]
0x18000624f  mov     rbx, rcx
0x180006252  mov     ebp, 50h ; 'P'
0x180006257  jnz     short loc_18000628E
0x180006259  test    edi, edi
0x18000625b  jz      short loc_18000628E
0x18000625d  mov     edx, 190h; dwBytes
0x180006262  lea     ecx, [rbp-48h]; dwFlags
0x180006265  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000626a  mov     [rbx+18h], rax
0x18000626e  test    rax, rax
0x180006271  jz      short loc_18000628E
0x180006273  mov     dword ptr [rbx+20h], 5
0x18000627a  lea     rcx, [rax+190h]
0x180006281  jmp     short loc_180006289
0x180006283  mov     [rax], bp
0x180006286  add     rax, rbp
0x180006289  cmp     rax, rcx
0x18000628c  jnz     short loc_180006283
0x18000628e  mov     r9, [rbx+18h]
0x180006292  test    r9, r9
0x180006295  jz      short loc_180006301
0x180006297  test    edi, edi
0x180006299  jz      short loc_1800062C7
0x18000629b  movzx   eax, word ptr [rbx+20h]
0x18000629f  mov     rcx, r9
0x1800062a2  lea     rdx, [rax+rax*4]
0x1800062a6  shl     rdx, 4
0x1800062aa  add     rdx, r9
0x1800062ad  cmp     rcx, rdx
0x1800062b0  jz      short loc_1800062C7
0x1800062b2  mov     eax, [rbx+10h]
0x1800062b5  cmp     [rcx+4], eax
0x1800062b8  jbe     short loc_1800062C2
0x1800062ba  mov     eax, [rsi+8]
0x1800062bd  cmp     [rcx+8], eax
0x1800062c0  jz      short loc_180006301
0x1800062c2  add     rcx, rbp
0x1800062c5  jmp     short loc_1800062AD
0x1800062c7  movzx   eax, word ptr [rbx+22h]
0x1800062cb  xor     edx, edx
0x1800062cd  movzx   ecx, word ptr [rbx+20h]
0x1800062d1  inc     eax
0x1800062d3  div     ecx
0x1800062d5  mov     rax, [rbx+8]
0x1800062d9  mov     r8d, 1
0x1800062df  mov     [rbx+22h], dx
0x1800062e3  lock xadd [rax], r8d
0x1800062e8  movzx   eax, dx
0x1800062eb  inc     r8d; unsigned int
0x1800062ee  mov     rdx, rsi; struct wil::FailureInfo *
0x1800062f1  lea     rcx, [rax+rax*4]
0x1800062f5  shl     rcx, 4
0x1800062f9  add     rcx, r9; this
0x1800062fc  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180006301  mov     rbx, [rsp+38h+arg_10]
0x180006306  add     rsp, 20h
0x18000630a  pop     rdi
0x18000630b  pop     rsi
0x18000630c  pop     rbp
0x18000630d  retn
```
