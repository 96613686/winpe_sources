# SXReadBase::GetQName(RStringPtr &,RStringPtr &,int,int *)

- ea: `0x1004100d0`
- end: `0x1004101d1`
- name: `?GetQName@SXReadBase@@IEAAPEA_WAEAVRStringPtr@@0HPEAH@Z`
- size: `257`
- prototype: `wchar_t *__fastcall(SXReadBase *this, struct RStringPtr *, struct RStringPtr *, int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x10040edb0`

## callees

- `0x100401350`
- `0x1004100d0`
- `0x100410e60`
- `0x100415d60`

## pseudocode

```c
wchar_t *__fastcall SXReadBase::GetQName(
        SXReadBase *this,
        struct RStringPtr *a2,
        struct RStringPtr *a3,
        int a4,
        int *a5)
{
  unsigned int v7; // ebx
  int v8; // r8d
  unsigned int v9; // eax
  wchar_t *WCharBuffer; // rax
  wchar_t *v11; // rdi
  unsigned __int64 v12; // rsi
  __int64 v13; // rcx
  __int64 v14; // rdx
  wchar_t *v15; // r9
  unsigned __int64 v16; // rcx
  size_t v17; // r8
  wchar_t *v18; // rcx
  unsigned __int64 v19; // rax

  v7 = *(_DWORD *)(*(_QWORD *)a3 + 16LL);
  v8 = *(_DWORD *)(*(_QWORD *)a2 + 16LL);
  if ( v8 )
  {
    v9 = v7 + 1;
    if ( !v7 )
      v9 = 0;
    v7 = v8 + v9;
  }
  WCharBuffer = SXReadBase::GetWCharBuffer(this, a4, v7);
  v11 = WCharBuffer;
  v12 = *(unsigned int *)(*(_QWORD *)a2 + 16LL);
  if ( !(_DWORD)v12 )
  {
    v14 = *(_QWORD *)a3;
    v19 = *(unsigned int *)(*(_QWORD *)a3 + 16LL);
    if ( v7 >= (unsigned int)v19 )
    {
      v17 = 2 * v19;
      if ( 2 * v19 >= v19 )
      {
        v18 = v11;
        goto LABEL_15;
      }
    }
LABEL_17:
    MXRRaiseException(-2147467259);
    JUMPOUT(0x1004101D0LL);
  }
  if ( v7 < (unsigned int)v12 || 2 * v12 < v12 )
    goto LABEL_17;
  memmove(WCharBuffer, (const void *)(*(_QWORD *)a2 + 24LL), 2 * v12);
  if ( *(_DWORD *)(*(_QWORD *)a3 + 16LL) )
  {
    v13 = *(unsigned int *)(*(_QWORD *)a2 + 16LL);
    v11[v13] = 58;
    v14 = *(_QWORD *)a3;
    v15 = &v11[v13];
    v16 = *(unsigned int *)(*(_QWORD *)a3 + 16LL);
    if ( v7 - (unsigned int)v12 - 1 >= (unsigned int)v16 )
    {
      v17 = 2 * v16;
      if ( 2 * v16 >= v16 )
      {
        v18 = v15 + 1;
LABEL_15:
        memmove(v18, (const void *)(v14 + 24), v17);
        goto LABEL_16;
      }
    }
    goto LABEL_17;
  }
LABEL_16:
  *a5 = v7;
  return v11;
}

```

## disassembly

```asm
0x1004100d0  mov     [rsp+arg_0], rbx
0x1004100d5  mov     [rsp+arg_8], rsi
0x1004100da  mov     [rsp+arg_10], rdi
0x1004100df  mov     [rsp+arg_18], r14
0x1004100e4  push    r15
0x1004100e6  sub     rsp, 20h
0x1004100ea  mov     rax, [r8]
0x1004100ed  mov     r14, r8
0x1004100f0  mov     r15, rdx
0x1004100f3  mov     ebx, [rax+10h]
0x1004100f6  mov     rax, [rdx]
0x1004100f9  mov     r8d, [rax+10h]
0x1004100fd  test    r8d, r8d
0x100410100  jz      short loc_10041010E
0x100410102  test    ebx, ebx
0x100410104  lea     eax, [rbx+1]
0x100410107  cmovz   eax, ebx
0x10041010a  lea     ebx, [r8+rax]
0x10041010e  mov     r8d, ebx; unsigned int
0x100410111  mov     edx, r9d; int
0x100410114  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x100410119  mov     rdx, [r15]
0x10041011c  mov     rdi, rax
0x10041011f  mov     esi, [rdx+10h]
0x100410122  test    esi, esi
0x100410124  jz      short loc_100410182
0x100410126  cmp     ebx, esi
0x100410128  jb      loc_1004101C6
0x10041012e  lea     r8, [rsi+rsi]; Size
0x100410132  cmp     r8, rsi
0x100410135  jb      loc_1004101C6
0x10041013b  add     rdx, 18h; Src
0x10041013f  mov     rcx, rax; void *
0x100410142  call    memmove
0x100410147  mov     rax, [r14]
0x10041014a  cmp     dword ptr [rax+10h], 0
0x10041014e  jz      short loc_1004101A1
0x100410150  mov     rax, [r15]
0x100410153  mov     ecx, [rax+10h]
0x100410156  mov     eax, 3Ah ; ':'
0x10041015b  mov     [rdi+rcx*2], ax
0x10041015f  mov     eax, ebx
0x100410161  mov     rdx, [r14]
0x100410164  sub     eax, esi
0x100410166  dec     eax
0x100410168  lea     r9, [rdi+rcx*2]
0x10041016c  mov     ecx, [rdx+10h]
0x10041016f  cmp     eax, ecx
0x100410171  jb      short loc_1004101C6
0x100410173  lea     r8, [rcx+rcx]
0x100410177  cmp     r8, rcx
0x10041017a  jb      short loc_1004101C6
0x10041017c  lea     rcx, [r9+2]
0x100410180  jmp     short loc_100410198
0x100410182  mov     rdx, [r14]
0x100410185  mov     eax, [rdx+10h]
0x100410188  cmp     ebx, eax
0x10041018a  jb      short loc_1004101C6
0x10041018c  lea     r8, [rax+rax]; Size
0x100410190  cmp     r8, rax
0x100410193  jb      short loc_1004101C6
0x100410195  mov     rcx, rdi; void *
0x100410198  add     rdx, 18h; Src
0x10041019c  call    memmove
0x1004101a1  mov     rax, [rsp+28h+arg_20]
0x1004101a6  mov     rsi, [rsp+28h+arg_8]
0x1004101ab  mov     r14, [rsp+28h+arg_18]
0x1004101b0  mov     [rax], ebx
0x1004101b2  mov     rax, rdi
0x1004101b5  mov     rdi, [rsp+28h+arg_10]
0x1004101ba  mov     rbx, [rsp+28h+arg_0]
0x1004101bf  add     rsp, 20h
0x1004101c3  pop     r15
0x1004101c5  retn
0x1004101c6  mov     ecx, 80004005h; int
0x1004101cb  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
