# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000a4b4`
- end: `0x18000a5b0`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `252`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006120`

## callees

- `0x180008344`
- `0x18000a120`
- `0x18000a4b4`

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
0x18000a4b4  mov     rax, rsp
0x18000a4b7  mov     [rax+8], rbx
0x18000a4bb  mov     [rax+10h], rbp
0x18000a4bf  mov     [rax+18h], rsi
0x18000a4c3  mov     [rax+20h], rdi
0x18000a4c7  push    r14
0x18000a4c9  sub     rsp, 20h
0x18000a4cd  mov     edi, [rcx+10h]
0x18000a4d0  xor     ebp, ebp
0x18000a4d2  mov     rsi, rdx
0x18000a4d5  mov     rbx, rcx
0x18000a4d8  lea     r14d, [rbp+50h]
0x18000a4dc  cmp     [rcx+18h], rbp
0x18000a4e0  jnz     short loc_18000A518
0x18000a4e2  test    edi, edi
0x18000a4e4  jz      short loc_18000A518
0x18000a4e6  mov     edx, 190h; dwBytes
0x18000a4eb  lea     ecx, [rbp+8]; dwFlags
0x18000a4ee  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a4f3  mov     [rbx+18h], rax
0x18000a4f7  test    rax, rax
0x18000a4fa  jz      short loc_18000A518
0x18000a4fc  mov     dword ptr [rbx+20h], 5
0x18000a503  lea     rcx, [rax+190h]
0x18000a50a  jmp     short loc_18000A513
0x18000a50c  mov     [rax], r14w
0x18000a510  add     rax, r14
0x18000a513  cmp     rax, rcx
0x18000a516  jnz     short loc_18000A50C
0x18000a518  mov     r8, [rbx+18h]
0x18000a51c  test    r8, r8
0x18000a51f  jz      short loc_18000A594
0x18000a521  test    edi, edi
0x18000a523  jz      short loc_18000A55A
0x18000a525  movzx   eax, word ptr [rbx+20h]
0x18000a529  lea     rcx, [rax+rax*4]
0x18000a52d  shl     rcx, 4
0x18000a531  add     rcx, r8
0x18000a534  cmp     r8, rcx
0x18000a537  jz      short loc_18000A55A
0x18000a539  mov     r9d, [rbx+10h]
0x18000a53d  lea     rdx, [r8+8]
0x18000a541  cmp     [rdx-4], r9d
0x18000a545  jbe     short loc_18000A54E
0x18000a547  mov     eax, [rsi+8]
0x18000a54a  cmp     [rdx], eax
0x18000a54c  jz      short loc_18000A594
0x18000a54e  add     rdx, r14
0x18000a551  lea     rax, [rdx-8]
0x18000a555  cmp     rax, rcx
0x18000a558  jnz     short loc_18000A541
0x18000a55a  movzx   eax, word ptr [rbx+22h]
0x18000a55e  xor     edx, edx
0x18000a560  movzx   ecx, word ptr [rbx+20h]
0x18000a564  inc     eax
0x18000a566  div     ecx
0x18000a568  movzx   eax, dx
0x18000a56b  mov     [rbx+22h], dx
0x18000a56f  lea     rcx, [rax+rax*4]
0x18000a573  mov     rax, [rbx+8]
0x18000a577  shl     rcx, 4
0x18000a57b  add     rcx, r8; this
0x18000a57e  mov     r8d, 1
0x18000a584  lock xadd [rax], r8d
0x18000a589  inc     r8d; unsigned int
0x18000a58c  mov     rdx, rsi; struct wil::FailureInfo *
0x18000a58f  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000a594  mov     rbx, [rsp+28h+arg_0]
0x18000a599  mov     rbp, [rsp+28h+arg_8]
0x18000a59e  mov     rsi, [rsp+28h+arg_10]
0x18000a5a3  mov     rdi, [rsp+28h+arg_18]
0x18000a5a8  add     rsp, 20h
0x18000a5ac  pop     r14
0x18000a5ae  retn
```
