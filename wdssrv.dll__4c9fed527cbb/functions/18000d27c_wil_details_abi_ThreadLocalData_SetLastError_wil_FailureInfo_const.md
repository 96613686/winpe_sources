# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000d27c`
- end: `0x18000d378`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `252`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009020`

## callees

- `0x18000ada8`
- `0x18000cee8`
- `0x18000d27c`

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
0x18000d27c  mov     rax, rsp
0x18000d27f  mov     [rax+8], rbx
0x18000d283  mov     [rax+10h], rbp
0x18000d287  mov     [rax+18h], rsi
0x18000d28b  mov     [rax+20h], rdi
0x18000d28f  push    r14
0x18000d291  sub     rsp, 20h
0x18000d295  mov     edi, [rcx+10h]
0x18000d298  xor     ebp, ebp
0x18000d29a  mov     rsi, rdx
0x18000d29d  mov     rbx, rcx
0x18000d2a0  lea     r14d, [rbp+50h]
0x18000d2a4  cmp     [rcx+18h], rbp
0x18000d2a8  jnz     short loc_18000D2E0
0x18000d2aa  test    edi, edi
0x18000d2ac  jz      short loc_18000D2E0
0x18000d2ae  mov     edx, 190h; dwBytes
0x18000d2b3  lea     ecx, [rbp+8]; dwFlags
0x18000d2b6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000d2bb  mov     [rbx+18h], rax
0x18000d2bf  test    rax, rax
0x18000d2c2  jz      short loc_18000D2E0
0x18000d2c4  mov     dword ptr [rbx+20h], 5
0x18000d2cb  lea     rcx, [rax+190h]
0x18000d2d2  jmp     short loc_18000D2DB
0x18000d2d4  mov     [rax], r14w
0x18000d2d8  add     rax, r14
0x18000d2db  cmp     rax, rcx
0x18000d2de  jnz     short loc_18000D2D4
0x18000d2e0  mov     r8, [rbx+18h]
0x18000d2e4  test    r8, r8
0x18000d2e7  jz      short loc_18000D35C
0x18000d2e9  test    edi, edi
0x18000d2eb  jz      short loc_18000D322
0x18000d2ed  movzx   eax, word ptr [rbx+20h]
0x18000d2f1  lea     rcx, [rax+rax*4]
0x18000d2f5  shl     rcx, 4
0x18000d2f9  add     rcx, r8
0x18000d2fc  cmp     r8, rcx
0x18000d2ff  jz      short loc_18000D322
0x18000d301  mov     r9d, [rbx+10h]
0x18000d305  lea     rdx, [r8+8]
0x18000d309  cmp     [rdx-4], r9d
0x18000d30d  jbe     short loc_18000D316
0x18000d30f  mov     eax, [rsi+8]
0x18000d312  cmp     [rdx], eax
0x18000d314  jz      short loc_18000D35C
0x18000d316  add     rdx, r14
0x18000d319  lea     rax, [rdx-8]
0x18000d31d  cmp     rax, rcx
0x18000d320  jnz     short loc_18000D309
0x18000d322  movzx   eax, word ptr [rbx+22h]
0x18000d326  xor     edx, edx
0x18000d328  movzx   ecx, word ptr [rbx+20h]
0x18000d32c  inc     eax
0x18000d32e  div     ecx
0x18000d330  movzx   eax, dx
0x18000d333  mov     [rbx+22h], dx
0x18000d337  lea     rcx, [rax+rax*4]
0x18000d33b  mov     rax, [rbx+8]
0x18000d33f  shl     rcx, 4
0x18000d343  add     rcx, r8; this
0x18000d346  mov     r8d, 1
0x18000d34c  lock xadd [rax], r8d
0x18000d351  inc     r8d; unsigned int
0x18000d354  mov     rdx, rsi; struct wil::FailureInfo *
0x18000d357  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000d35c  mov     rbx, [rsp+28h+arg_0]
0x18000d361  mov     rbp, [rsp+28h+arg_8]
0x18000d366  mov     rsi, [rsp+28h+arg_10]
0x18000d36b  mov     rdi, [rsp+28h+arg_18]
0x18000d370  add     rsp, 20h
0x18000d374  pop     r14
0x18000d376  retn
```
