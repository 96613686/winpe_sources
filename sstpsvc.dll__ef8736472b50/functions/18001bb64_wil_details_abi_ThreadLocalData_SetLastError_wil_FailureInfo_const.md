# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18001bb64`
- end: `0x18001bc39`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `213`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180019550`

## callees

- `0x18001aa40`
- `0x18001b928`
- `0x18001bb64`

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
  __int64 v8; // rcx
  __int64 v9; // rdx
  unsigned __int16 v10; // dx
  volatile signed __int32 *v11; // rax

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
    if ( !v3 || (v8 = *((_QWORD *)this + 3), v9 = v7 + 80LL * *((unsigned __int16 *)this + 16), v7 == v9) )
    {
LABEL_13:
      v10 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
      v11 = (volatile signed __int32 *)*((_QWORD *)this + 1);
      *((_WORD *)this + 17) = v10;
      wil::details_abi::ThreadLocalFailureInfo::Set(
        (wil::details_abi::ThreadLocalFailureInfo *)(v7 + 80LL * v10),
        a2,
        _InterlockedIncrement(v11));
    }
    else
    {
      while ( *(_DWORD *)(v8 + 4) <= *((_DWORD *)this + 4) || *(_DWORD *)(v8 + 8) != *((_DWORD *)a2 + 2) )
      {
        v8 += 80;
        if ( v8 == v9 )
          goto LABEL_13;
      }
    }
  }
}

```

## disassembly

```asm
0x18001bb64  push    rbx
0x18001bb66  push    rbp
0x18001bb67  push    rsi
0x18001bb68  push    rdi
0x18001bb69  sub     rsp, 28h
0x18001bb6d  cmp     qword ptr [rcx+18h], 0
0x18001bb72  mov     rsi, rdx
0x18001bb75  mov     edi, [rcx+10h]
0x18001bb78  mov     rbx, rcx
0x18001bb7b  mov     ebp, 50h ; 'P'
0x18001bb80  jnz     short loc_18001BBB7
0x18001bb82  test    edi, edi
0x18001bb84  jz      short loc_18001BBB7
0x18001bb86  mov     edx, 190h; dwBytes
0x18001bb8b  lea     ecx, [rbp-48h]; dwFlags
0x18001bb8e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001bb93  mov     [rbx+18h], rax
0x18001bb97  test    rax, rax
0x18001bb9a  jz      short loc_18001BBB7
0x18001bb9c  mov     dword ptr [rbx+20h], 5
0x18001bba3  lea     rcx, [rax+190h]
0x18001bbaa  jmp     short loc_18001BBB2
0x18001bbac  mov     [rax], bp
0x18001bbaf  add     rax, rbp
0x18001bbb2  cmp     rax, rcx
0x18001bbb5  jnz     short loc_18001BBAC
0x18001bbb7  mov     r9, [rbx+18h]
0x18001bbbb  test    r9, r9
0x18001bbbe  jz      short loc_18001BC2F
0x18001bbc0  test    edi, edi
0x18001bbc2  jz      short loc_18001BBF5
0x18001bbc4  movzx   eax, word ptr [rbx+20h]
0x18001bbc8  mov     rcx, r9
0x18001bbcb  lea     rdx, [rax+rax*4]
0x18001bbcf  shl     rdx, 4
0x18001bbd3  add     rdx, r9
0x18001bbd6  cmp     r9, rdx
0x18001bbd9  jz      short loc_18001BBF5
0x18001bbdb  mov     r8d, [rbx+10h]
0x18001bbdf  cmp     [rcx+4], r8d
0x18001bbe3  jbe     short loc_18001BBED
0x18001bbe5  mov     eax, [rsi+8]
0x18001bbe8  cmp     [rcx+8], eax
0x18001bbeb  jz      short loc_18001BC2F
0x18001bbed  add     rcx, rbp
0x18001bbf0  cmp     rcx, rdx
0x18001bbf3  jnz     short loc_18001BBDF
0x18001bbf5  movzx   eax, word ptr [rbx+22h]
0x18001bbf9  xor     edx, edx
0x18001bbfb  movzx   ecx, word ptr [rbx+20h]
0x18001bbff  inc     eax
0x18001bc01  div     ecx
0x18001bc03  mov     rax, [rbx+8]
0x18001bc07  mov     r8d, 1
0x18001bc0d  mov     [rbx+22h], dx
0x18001bc11  lock xadd [rax], r8d
0x18001bc16  movzx   eax, dx
0x18001bc19  inc     r8d; unsigned int
0x18001bc1c  mov     rdx, rsi; struct wil::FailureInfo *
0x18001bc1f  lea     rcx, [rax+rax*4]
0x18001bc23  shl     rcx, 4
0x18001bc27  add     rcx, r9; this
0x18001bc2a  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18001bc2f  add     rsp, 28h
0x18001bc33  pop     rdi
0x18001bc34  pop     rsi
0x18001bc35  pop     rbp
0x18001bc36  pop     rbx
0x18001bc37  retn
```
