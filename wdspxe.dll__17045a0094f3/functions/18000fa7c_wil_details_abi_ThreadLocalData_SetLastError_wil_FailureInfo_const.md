# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000fa7c`
- end: `0x18000fb78`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `252`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b610`

## callees

- `0x18000ce30`
- `0x18000f64c`
- `0x18000fa7c`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v2; // edi
  _WORD *v5; // rax
  _WORD *v6; // rcx
  _DWORD *v7; // r8
  _DWORD *v8; // rcx
  _DWORD *v9; // rdx
  unsigned __int16 v10; // dx

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
  if ( v7 )
  {
    if ( !v2 || (v8 = &v7[20 * *((unsigned __int16 *)this + 16)], v7 == v8) )
    {
LABEL_14:
      v10 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
      *((_WORD *)this + 17) = v10;
      wil::details_abi::ThreadLocalFailureInfo::Set(
        (wil::details_abi::ThreadLocalFailureInfo *)&v7[20 * v10],
        a2,
        _InterlockedIncrement(*((volatile signed __int32 **)this + 1)));
    }
    else
    {
      v9 = v7 + 2;
      while ( *(v9 - 1) <= *((_DWORD *)this + 4) || *v9 != *((_DWORD *)a2 + 2) )
      {
        v9 += 20;
        if ( v9 - 2 == v8 )
          goto LABEL_14;
      }
    }
  }
}

```

## disassembly

```asm
0x18000fa7c  mov     rax, rsp
0x18000fa7f  mov     [rax+8], rbx
0x18000fa83  mov     [rax+10h], rbp
0x18000fa87  mov     [rax+18h], rsi
0x18000fa8b  mov     [rax+20h], rdi
0x18000fa8f  push    r14
0x18000fa91  sub     rsp, 20h
0x18000fa95  mov     edi, [rcx+10h]
0x18000fa98  xor     ebp, ebp
0x18000fa9a  mov     rsi, rdx
0x18000fa9d  mov     rbx, rcx
0x18000faa0  lea     r14d, [rbp+50h]
0x18000faa4  cmp     [rcx+18h], rbp
0x18000faa8  jnz     short loc_18000FAE0
0x18000faaa  test    edi, edi
0x18000faac  jz      short loc_18000FAE0
0x18000faae  mov     edx, 190h; dwBytes
0x18000fab3  lea     ecx, [rbp+8]; dwFlags
0x18000fab6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000fabb  mov     [rbx+18h], rax
0x18000fabf  test    rax, rax
0x18000fac2  jz      short loc_18000FAE0
0x18000fac4  mov     dword ptr [rbx+20h], 5
0x18000facb  lea     rcx, [rax+190h]
0x18000fad2  jmp     short loc_18000FADB
0x18000fad4  mov     [rax], r14w
0x18000fad8  add     rax, r14
0x18000fadb  cmp     rax, rcx
0x18000fade  jnz     short loc_18000FAD4
0x18000fae0  mov     r8, [rbx+18h]
0x18000fae4  test    r8, r8
0x18000fae7  jz      short loc_18000FB5C
0x18000fae9  test    edi, edi
0x18000faeb  jz      short loc_18000FB22
0x18000faed  movzx   eax, word ptr [rbx+20h]
0x18000faf1  lea     rcx, [rax+rax*4]
0x18000faf5  shl     rcx, 4
0x18000faf9  add     rcx, r8
0x18000fafc  cmp     r8, rcx
0x18000faff  jz      short loc_18000FB22
0x18000fb01  mov     r9d, [rbx+10h]
0x18000fb05  lea     rdx, [r8+8]
0x18000fb09  cmp     [rdx-4], r9d
0x18000fb0d  jbe     short loc_18000FB16
0x18000fb0f  mov     eax, [rsi+8]
0x18000fb12  cmp     [rdx], eax
0x18000fb14  jz      short loc_18000FB5C
0x18000fb16  add     rdx, r14
0x18000fb19  lea     rax, [rdx-8]
0x18000fb1d  cmp     rax, rcx
0x18000fb20  jnz     short loc_18000FB09
0x18000fb22  movzx   eax, word ptr [rbx+22h]
0x18000fb26  xor     edx, edx
0x18000fb28  movzx   ecx, word ptr [rbx+20h]
0x18000fb2c  inc     eax
0x18000fb2e  div     ecx
0x18000fb30  movzx   eax, dx
0x18000fb33  mov     [rbx+22h], dx
0x18000fb37  lea     rcx, [rax+rax*4]
0x18000fb3b  mov     rax, [rbx+8]
0x18000fb3f  shl     rcx, 4
0x18000fb43  add     rcx, r8; this
0x18000fb46  mov     r8d, 1
0x18000fb4c  lock xadd [rax], r8d
0x18000fb51  inc     r8d; unsigned int
0x18000fb54  mov     rdx, rsi; struct wil::FailureInfo *
0x18000fb57  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000fb5c  mov     rbx, [rsp+28h+arg_0]
0x18000fb61  mov     rbp, [rsp+28h+arg_8]
0x18000fb66  mov     rsi, [rsp+28h+arg_10]
0x18000fb6b  mov     rdi, [rsp+28h+arg_18]
0x18000fb70  add     rsp, 20h
0x18000fb74  pop     r14
0x18000fb76  retn
```
