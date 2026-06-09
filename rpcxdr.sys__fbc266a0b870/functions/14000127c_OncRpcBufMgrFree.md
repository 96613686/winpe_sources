# OncRpcBufMgrFree

- ea: `0x14000127c`
- end: `0x140001338`
- name: `OncRpcBufMgrFree`
- size: `188`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140004600`
- `0x14000fabc`

## callees

- `0x1400010dc`
- `0x14000127c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140001315`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140001315`

## pseudocode

```c
void __fastcall OncRpcBufMgrFree(char *Entry)
{
  _QWORD **v2; // rdi
  int i; // ebx
  _QWORD *v4; // rcx
  _QWORD *v5; // rax
  int v6; // ebx
  int v7; // ebx

  v2 = (_QWORD **)(Entry + 24);
  for ( i = 0; ; ++i )
  {
    v4 = *v2;
    if ( *v2 == v2 )
      break;
    if ( (_QWORD **)v4[1] != v2 || (v5 = (_QWORD *)*v4, *(_QWORD **)(*v4 + 8LL) != v4) )
      __fastfail(3u);
    *v2 = v5;
    v5[1] = v2;
    OncRpcBufMgrBufferDescriptorDeref(v4 - 3);
  }
  if ( i )
  {
    v6 = i - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        if ( v7 == 1 )
          ++qword_14001A6D8;
        else
          ++qword_14001A6E0;
      }
      else
      {
        ++qword_14001A6D0;
      }
    }
    else
    {
      ++qword_14001A6C8;
    }
  }
  else
  {
    ++qword_14001A6C0;
  }
  if ( (*((_DWORD *)Entry + 14) & 1) != 0 )
  {
    ExFreeToNPagedLookasideList(&Lookaside, Entry);
    --dword_14001A6E8;
  }
}

```

## disassembly

```asm
0x14000127c  mov     [rsp+arg_0], rbx
0x140001281  mov     [rsp+arg_8], rsi
0x140001286  push    rdi
0x140001287  sub     rsp, 20h
0x14000128b  mov     rsi, rcx
0x14000128e  lea     rdi, [rcx+18h]
0x140001292  xor     ebx, ebx
0x140001294  mov     rcx, [rdi]
0x140001297  cmp     rcx, rdi
0x14000129a  jz      short loc_1400012C6
0x14000129c  cmp     [rcx+8], rdi
0x1400012a0  jnz     short loc_1400012BF
0x1400012a2  mov     rax, [rcx]
0x1400012a5  cmp     [rax+8], rcx
0x1400012a9  jnz     short loc_1400012BF
0x1400012ab  mov     [rdi], rax
0x1400012ae  add     rcx, 0FFFFFFFFFFFFFFE8h
0x1400012b2  mov     [rax+8], rdi
0x1400012b6  call    OncRpcBufMgrBufferDescriptorDeref
0x1400012bb  inc     ebx
0x1400012bd  jmp     short loc_140001294
0x1400012bf  mov     ecx, 3
0x1400012c4  int     29h; Win8: RtlFailFast(ecx)
0x1400012c6  test    ebx, ebx
0x1400012c8  jz      short loc_1400012FD
0x1400012ca  sub     ebx, 1
0x1400012cd  jz      short loc_1400012F4
0x1400012cf  sub     ebx, 1
0x1400012d2  jz      short loc_1400012EB
0x1400012d4  cmp     ebx, 1
0x1400012d7  jz      short loc_1400012E2
0x1400012d9  inc     cs:qword_14001A6E0
0x1400012e0  jmp     short loc_140001304
0x1400012e2  inc     cs:qword_14001A6D8
0x1400012e9  jmp     short loc_140001304
0x1400012eb  inc     cs:qword_14001A6D0
0x1400012f2  jmp     short loc_140001304
0x1400012f4  inc     cs:qword_14001A6C8
0x1400012fb  jmp     short loc_140001304
0x1400012fd  inc     cs:qword_14001A6C0
0x140001304  mov     eax, [rsi+38h]
0x140001307  test    al, 1
0x140001309  jz      short loc_140001327
0x14000130b  mov     rdx, rsi; Entry
0x14000130e  lea     rcx, Lookaside; Lookaside
0x140001315  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000131c  nop     dword ptr [rax+rax+00h]
0x140001321  dec     cs:dword_14001A6E8
0x140001327  mov     rbx, [rsp+28h+arg_0]
0x14000132c  mov     rsi, [rsp+28h+arg_8]
0x140001331  add     rsp, 20h
0x140001335  pop     rdi
0x140001336  retn
```
