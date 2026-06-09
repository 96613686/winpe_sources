# YReader::GetProperty(int,tagVARIANT *)

- ea: `0x100403230`
- end: `0x100403490`
- name: `?GetProperty@YReader@@UEAAJHPEAUtagVARIANT@@@Z`
- size: `608`
- prototype: `__int64 __fastcall(YReader *__hidden this, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x100403230`
- `0x1004394f0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1004032bd`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1004032bd`

## pseudocode

```c
__int64 __fastcall YReader::GetProperty(YReader *this, int a2, struct tagVARIANT *a3)
{
  unsigned int v3; // esi
  unsigned int v6; // eax
  __int64 result; // rax
  UINT v8; // edx
  const OLECHAR *v9; // rcx
  BSTR v10; // rax
  unsigned int v11; // eax

  v3 = 0;
  switch ( a2 )
  {
    case 0:
      a3->vt = 8;
      v6 = *((_DWORD *)this + 422);
      if ( v6 == dword_100450B38 && !memcmp(*((const void **)this + 210), CodeStringPtr::empty, 2LL * v6) )
        goto LABEL_4;
      v8 = *((_DWORD *)this + 422);
      v9 = (const OLECHAR *)*((_QWORD *)this + 210);
      goto LABEL_6;
    case 1:
      a3->vt = 8;
      v11 = *((_DWORD *)this + 426);
      if ( v11 == dword_100450B38 && !memcmp(*((const void **)this + 212), CodeStringPtr::empty, 2LL * v11) )
      {
LABEL_4:
        a3->llVal = 0;
        return 0;
      }
      else
      {
        v8 = *((_DWORD *)this + 426);
        v9 = (const OLECHAR *)*((_QWORD *)this + 212);
LABEL_6:
        v10 = SysAllocStringLen(v9, v8);
        a3->llVal = (LONGLONG)v10;
        if ( v10 )
          return v3;
        else
          return 2147942414LL;
      }
    case 2:
      a3->vt = 11;
      result = 0;
      a3->iVal = -(*((_BYTE *)this + 1756) != 0);
      return result;
    case 3:
      a3->vt = 11;
      result = 0;
      a3->iVal = -(*((_BYTE *)this + 1757) != 0);
      return result;
    case 4:
      a3->vt = 11;
      result = 0;
      a3->iVal = -(*((_BYTE *)this + 1759) != 0);
      return result;
    case 5:
      a3->vt = 3;
      a3->lVal = *((_DWORD *)this + 450);
      return 0;
    case 6:
      a3->vt = 11;
      result = 0;
      a3->iVal = -(*((_BYTE *)this + 1760) != 0);
      return result;
    case 7:
      a3->vt = 3;
      a3->lVal = *((_DWORD *)this + 451);
      return 0;
    case 8:
      a3->vt = 11;
      result = 0;
      a3->iVal = -(*((_BYTE *)this + 1764) != 0);
      return result;
    default:
      return (unsigned int)-2147024809;
  }
}

```

## disassembly

```asm
0x100403230  mov     [rsp+arg_0], rbx
0x100403235  mov     [rsp+arg_8], rsi
0x10040323a  push    rdi
0x10040323b  sub     rsp, 20h
0x10040323f  xor     esi, esi
0x100403241  mov     rbx, r8
0x100403244  mov     rdi, rcx
0x100403247  cmp     edx, 8; switch 9 cases
0x10040324a  ja      def_100403264; jumptable 0000000100403264 default case
0x100403250  movsxd  rax, edx
0x100403253  lea     rcx, __ImageBase
0x10040325a  mov     edx, ds:(jpt_100403264 - 100400000h)[rcx+rax*4]
0x100403261  add     rdx, rcx
0x100403264  jmp     rdx; switch jump
0x100403266  mov     eax, 8; jumptable 0000000100403264 case 0
0x10040326b  mov     [r8], ax
0x10040326f  mov     eax, [rdi+698h]
0x100403275  cmp     eax, cs:dword_100450B38
0x10040327b  jnz     short loc_1004032B0
0x10040327d  mov     rdx, cs:?empty@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100403284  mov     r8d, eax
0x100403287  mov     rcx, [rdi+690h]; Buf1
0x10040328e  add     r8, r8; Size
0x100403291  call    memcmp
0x100403296  test    eax, eax
0x100403298  jnz     short loc_1004032B0
0x10040329a  mov     [rbx+8], rsi
0x10040329e  mov     eax, esi
0x1004032a0  mov     rbx, [rsp+28h+arg_0]
0x1004032a5  mov     rsi, [rsp+28h+arg_8]
0x1004032aa  add     rsp, 20h
0x1004032ae  pop     rdi
0x1004032af  retn
0x1004032b0  mov     edx, [rdi+698h]; ui
0x1004032b6  mov     rcx, [rdi+690h]; strIn
0x1004032bd  call    cs:__imp_SysAllocStringLen
0x1004032c3  mov     [rbx+8], rax
0x1004032c7  test    rax, rax
0x1004032ca  jnz     loc_100403459
0x1004032d0  mov     esi, 8007000Eh
0x1004032d5  mov     eax, esi
0x1004032d7  mov     rbx, [rsp+28h+arg_0]
0x1004032dc  mov     rsi, [rsp+28h+arg_8]
0x1004032e1  add     rsp, 20h
0x1004032e5  pop     rdi
0x1004032e6  retn
0x1004032e7  mov     eax, 8; jumptable 0000000100403264 case 1
0x1004032ec  mov     [r8], ax
0x1004032f0  mov     eax, [rdi+6A8h]
0x1004032f6  cmp     eax, cs:dword_100450B38
0x1004032fc  jnz     short loc_10040331F
0x1004032fe  mov     rdx, cs:?empty@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100403305  mov     r8d, eax
0x100403308  mov     rcx, [rdi+6A0h]; Buf1
0x10040330f  add     r8, r8; Size
0x100403312  call    memcmp
0x100403317  test    eax, eax
0x100403319  jz      loc_10040329A
0x10040331f  mov     edx, [rdi+6A8h]
0x100403325  mov     rcx, [rdi+6A0h]
0x10040332c  jmp     short loc_1004032BD
0x10040332e  mov     eax, 0Bh; jumptable 0000000100403264 case 2
0x100403333  mov     [r8], ax
0x100403337  movzx   eax, byte ptr [rdi+6DCh]
0x10040333e  neg     al
0x100403340  mov     eax, esi
0x100403342  sbb     cx, cx
0x100403345  mov     [r8+8], cx
0x10040334a  mov     rbx, [rsp+28h+arg_0]
0x10040334f  mov     rsi, [rsp+28h+arg_8]
0x100403354  add     rsp, 20h
0x100403358  pop     rdi
0x100403359  retn
0x10040335a  mov     eax, 0Bh; jumptable 0000000100403264 case 3
0x10040335f  mov     [r8], ax
0x100403363  movzx   eax, byte ptr [rdi+6DDh]
0x10040336a  neg     al
0x10040336c  mov     eax, esi
0x10040336e  sbb     cx, cx
0x100403371  mov     [r8+8], cx
0x100403376  mov     rbx, [rsp+28h+arg_0]
0x10040337b  mov     rsi, [rsp+28h+arg_8]
0x100403380  add     rsp, 20h
0x100403384  pop     rdi
0x100403385  retn
0x100403386  mov     eax, 0Bh; jumptable 0000000100403264 case 4
0x10040338b  mov     [r8], ax
0x10040338f  movzx   eax, byte ptr [rdi+6DFh]
0x100403396  neg     al
0x100403398  mov     eax, esi
0x10040339a  sbb     cx, cx
0x10040339d  mov     [r8+8], cx
0x1004033a2  mov     rbx, [rsp+28h+arg_0]
0x1004033a7  mov     rsi, [rsp+28h+arg_8]
0x1004033ac  add     rsp, 20h
0x1004033b0  pop     rdi
0x1004033b1  retn
0x1004033b2  mov     eax, 3; jumptable 0000000100403264 case 5
0x1004033b7  mov     [r8], ax
0x1004033bb  mov     eax, [rdi+708h]
0x1004033c1  mov     [r8+8], eax
0x1004033c5  mov     eax, esi
0x1004033c7  mov     rbx, [rsp+28h+arg_0]
0x1004033cc  mov     rsi, [rsp+28h+arg_8]
0x1004033d1  add     rsp, 20h
0x1004033d5  pop     rdi
0x1004033d6  retn
0x1004033d7  mov     eax, 0Bh; jumptable 0000000100403264 case 6
0x1004033dc  mov     [r8], ax
0x1004033e0  movzx   eax, byte ptr [rdi+6E0h]
0x1004033e7  neg     al
0x1004033e9  mov     eax, esi
0x1004033eb  sbb     cx, cx
0x1004033ee  mov     [r8+8], cx
0x1004033f3  mov     rbx, [rsp+28h+arg_0]
0x1004033f8  mov     rsi, [rsp+28h+arg_8]
0x1004033fd  add     rsp, 20h
0x100403401  pop     rdi
0x100403402  retn
0x100403403  mov     eax, 3; jumptable 0000000100403264 case 7
0x100403408  mov     [r8], ax
0x10040340c  mov     eax, [rdi+70Ch]
0x100403412  mov     [r8+8], eax
0x100403416  mov     eax, esi
0x100403418  mov     rbx, [rsp+28h+arg_0]
0x10040341d  mov     rsi, [rsp+28h+arg_8]
0x100403422  add     rsp, 20h
0x100403426  pop     rdi
0x100403427  retn
0x100403428  mov     eax, 0Bh; jumptable 0000000100403264 case 8
0x10040342d  mov     [r8], ax
0x100403431  movzx   eax, byte ptr [rdi+6E4h]
0x100403438  neg     al
0x10040343a  mov     eax, esi
0x10040343c  sbb     cx, cx
0x10040343f  mov     [r8+8], cx
0x100403444  mov     rbx, [rsp+28h+arg_0]
0x100403449  mov     rsi, [rsp+28h+arg_8]
0x10040344e  add     rsp, 20h
0x100403452  pop     rdi
0x100403453  retn
0x100403454  mov     esi, 80070057h; jumptable 0000000100403264 default case
0x100403459  mov     rbx, [rsp+28h+arg_0]
0x10040345e  mov     eax, esi
0x100403460  mov     rsi, [rsp+28h+arg_8]
0x100403465  add     rsp, 20h
0x100403469  pop     rdi
0x10040346a  retn
```
