# OutputHelper::_hardWrite(void)

- ea: `0x1004228c0`
- end: `0x100422982`
- name: `?_hardWrite@OutputHelper@@IEAAXXZ`
- size: `194`
- prototype: `void __fastcall(OutputHelper *__hidden this)`
- caller_count: `21`
- callee_count: `4`
- tags: ``

## callers

- `0x10041bff0`
- `0x10041c070`
- `0x10041c100`
- `0x10041c1b0`
- `0x10041c2d0`
- `0x10041c400`
- `0x10041c560`
- `0x10041c660`
- `0x10041c6c0`
- `0x10041c700`
- `0x10041c7d0`
- `0x10041c850`
- `0x1004214b0`
- `0x1004216e0`
- `0x100421840`
- `0x1004219a0`
- `0x100421f10`
- `0x100422200`
- `0x100422990`
- `0x100422ac0`
- `0x100422b70`

## callees

- `0x100401780`
- `0x1004228c0`
- `0x100423100`
- `0x100439df0`

## pseudocode

```c
void __fastcall OutputHelper::_hardWrite(OutputHelper *this)
{
  __int64 v1; // r8
  int v2; // edi
  __int16 v4; // ax
  __int64 v5; // r8
  wchar_t *v6; // rdx
  unsigned int v7; // r8d
  EncodingWriter *v8; // rcx
  int v9; // eax

  v1 = *((_QWORD *)this + 3);
  v2 = 0;
  v4 = *(_WORD *)(v1 - 2);
  *((_WORD *)this + 120) = v4;
  v5 = (unsigned int)(v1 - *((_DWORD *)this + 10));
  v6 = (wchar_t *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 3) = v6;
  if ( !*((_BYTE *)this + 60) && *((_QWORD *)this + 29) )
  {
    if ( *((_BYTE *)this + 63) )
    {
      v7 = (unsigned int)v5 >> 1;
      v8 = (OutputHelper *)((char *)this + 64);
      if ( (unsigned __int16)(v4 + 10240) > 0x3FFu )
      {
        v9 = EncodingWriter::WriteString(v8, v6, v7);
      }
      else
      {
        v9 = EncodingWriter::WriteString(v8, v6, v7 - 1);
        v6 = (wchar_t *)*((_QWORD *)this + 5);
        *v6 = *((_WORD *)this + 120);
        *((_QWORD *)this + 3) += 2LL;
      }
    }
    else
    {
      v9 = (**((__int64 (__fastcall ***)(char *, wchar_t *, __int64))this + 2))((char *)this + 16, v6, v5);
    }
    v2 = v9;
  }
  (*(void (__fastcall **)(OutputHelper *, wchar_t *, __int64))(*(_QWORD *)this + 8LL))(this, v6, v5);
  if ( v2 < 0 )
  {
    _mm_lfence();
    *((_BYTE *)this + 60) = 1;
    MXRRaiseException(v2);
    JUMPOUT(0x100422981LL);
  }
}

```

## disassembly

```asm
0x1004228c0  mov     [rsp+arg_0], rbx
0x1004228c5  push    rdi
0x1004228c6  sub     rsp, 20h
0x1004228ca  mov     r8, [rcx+18h]
0x1004228ce  xor     edi, edi
0x1004228d0  mov     rbx, rcx
0x1004228d3  movzx   eax, word ptr [r8-2]
0x1004228d8  mov     [rcx+0F0h], ax
0x1004228df  sub     r8d, [rcx+28h]
0x1004228e3  mov     rdx, [rcx+28h]; wchar_t *
0x1004228e7  mov     [rcx+18h], rdx
0x1004228eb  cmp     [rcx+3Ch], dil
0x1004228ef  jnz     short loc_100422954
0x1004228f1  cmp     [rcx+0E8h], rdi
0x1004228f8  jz      short loc_100422954
0x1004228fa  cmp     [rcx+3Fh], dil
0x1004228fe  jz      short loc_100422941
0x100422900  mov     r9d, 2800h
0x100422906  shr     r8d, 1; unsigned int
0x100422909  add     ax, r9w
0x10042290d  add     rcx, 40h ; '@'; this
0x100422911  mov     r9d, 3FFh
0x100422917  cmp     ax, r9w
0x10042291b  ja      short loc_10042293A
0x10042291d  dec     r8d; unsigned int
0x100422920  call    ?WriteString@EncodingWriter@@QEAAJPEB_WI@Z; EncodingWriter::WriteString(wchar_t const *,uint)
0x100422925  mov     rdx, [rbx+28h]
0x100422929  movzx   ecx, word ptr [rbx+0F0h]
0x100422930  mov     [rdx], cx
0x100422933  add     qword ptr [rbx+18h], 2
0x100422938  jmp     short loc_100422952
0x10042293a  call    ?WriteString@EncodingWriter@@QEAAJPEB_WI@Z; EncodingWriter::WriteString(wchar_t const *,uint)
0x10042293f  jmp     short loc_100422952
0x100422941  mov     rax, [rcx+10h]
0x100422945  add     rcx, 10h
0x100422949  mov     rax, [rax]
0x10042294c  call    cs:__guard_dispatch_icall_fptr
0x100422952  mov     edi, eax
0x100422954  mov     rax, [rbx]
0x100422957  mov     rcx, rbx
0x10042295a  mov     rax, [rax+8]
0x10042295e  call    cs:__guard_dispatch_icall_fptr
0x100422964  test    edi, edi
0x100422966  js      short loc_100422973
0x100422968  mov     rbx, [rsp+28h+arg_0]
0x10042296d  add     rsp, 20h
0x100422971  pop     rdi
0x100422972  retn
0x100422973  lfence
0x100422976  mov     ecx, edi; int
0x100422978  mov     byte ptr [rbx+3Ch], 1
0x10042297c  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
