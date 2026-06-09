# YReader::ExpandAttributeValue(StringPtr *,StringPtr *,StringPtr *)

- ea: `0x10040bb50`
- end: `0x10040bc75`
- name: `?ExpandAttributeValue@YReader@@AEAAXPEAUStringPtr@@00@Z`
- size: `293`
- prototype: `void __fastcall(YReader *this, struct StringPtr *, struct StringPtr *, struct StringPtr *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x10040b880`
- `0x10040bc80`

## callees

- `0x100401780`
- `0x10040abb0`
- `0x10040bb50`
- `0x10040bc80`
- `0x100415490`
- `0x100425d50`

## pseudocode

```c
void __fastcall YReader::ExpandAttributeValue(
        YReader *this,
        struct StringPtr *a2,
        struct StringPtr *a3,
        struct StringPtr *a4)
{
  struct DeclEntity *v8; // rax
  struct DeclEntity *v9; // rbx
  void *v10; // rax
  void *v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // edx

  v8 = YReader::CheckEntity(this, a3, 1);
  v9 = v8;
  if ( v8 )
  {
    if ( *((_BYTE *)v8 + 132) )
    {
      *((_DWORD *)a2 + 2) += *((_DWORD *)v8 + 26) - *((_DWORD *)a3 + 2);
      v11 = BlockAlloc::ReallocData((YReader *)((char *)this + 416), *(void **)a2, 2 * *((_DWORD *)a2 + 2));
      *(_QWORD *)a4 = v11;
      *(_QWORD *)a2 = v11;
      v12 = *((unsigned int *)a4 + 2);
      v13 = *((_DWORD *)v9 + 26);
      if ( *((_DWORD *)a2 + 2) - (int)v12 < v13 )
      {
        MXRRaiseException(-2147467259);
        JUMPOUT(0x10040BC74LL);
      }
      memmove((void *)(*(_QWORD *)a4 + 2 * v12), *((const void **)v9 + 12), 2LL * v13);
      *((_DWORD *)a4 + 2) += *((_DWORD *)v9 + 26);
    }
    else
    {
      if ( *((_QWORD *)v8 + 17) )
      {
        MXRRaiseException(-1072894395);
        __debugbreak();
      }
      *((_QWORD *)v8 + 17) = this;
      *((_DWORD *)a2 + 2) += *((_DWORD *)v8 + 26) - *((_DWORD *)a3 + 2);
      v10 = BlockAlloc::ReallocData((YReader *)((char *)this + 416), *(void **)a2, 2 * *((_DWORD *)a2 + 2));
      *(_QWORD *)a4 = v10;
      *(_QWORD *)a2 = v10;
      YReader::FillAttributeValue(this, a2, (unsigned __int16 **)v9 + 12, a4);
      *((_QWORD *)v9 + 17) = 0;
    }
  }
}

```

## disassembly

```asm
0x10040bb50  mov     [rsp+arg_0], rbx
0x10040bb55  mov     [rsp+arg_8], rbp
0x10040bb5a  mov     [rsp+arg_10], rsi
0x10040bb5f  mov     [rsp+arg_18], rdi
0x10040bb64  push    r14
0x10040bb66  sub     rsp, 20h
0x10040bb6a  mov     r14, r8
0x10040bb6d  mov     rdi, rdx
0x10040bb70  mov     rdx, r14; struct StringPtr *
0x10040bb73  mov     r8b, 1; bool
0x10040bb76  mov     rsi, r9
0x10040bb79  mov     rbp, rcx
0x10040bb7c  call    ?CheckEntity@YReader@@AEAAPEAVDeclEntity@@PEAUStringPtr@@_N@Z; YReader::CheckEntity(StringPtr *,bool)
0x10040bb81  mov     rbx, rax
0x10040bb84  test    rax, rax
0x10040bb87  jz      loc_10040BC44
0x10040bb8d  cmp     byte ptr [rax+84h], 0
0x10040bb94  jnz     short loc_10040BBF0
0x10040bb96  cmp     qword ptr [rax+88h], 0
0x10040bb9e  jnz     loc_10040BC5F
0x10040bba4  mov     [rax+88h], rbp
0x10040bbab  lea     rcx, [rbp+1A0h]; this
0x10040bbb2  mov     eax, [rax+68h]
0x10040bbb5  sub     eax, [r14+8]
0x10040bbb9  add     [rdi+8], eax
0x10040bbbc  mov     r8d, [rdi+8]
0x10040bbc0  mov     rdx, [rdi]; void *
0x10040bbc3  add     r8d, r8d; unsigned int
0x10040bbc6  call    ?ReallocData@BlockAlloc@@QEAAPEAXPEAXK@Z; BlockAlloc::ReallocData(void *,ulong)
0x10040bbcb  mov     [rsi], rax
0x10040bbce  lea     r8, [rbx+60h]; struct StringPtr *
0x10040bbd2  mov     r9, rsi; struct StringPtr *
0x10040bbd5  mov     [rdi], rax
0x10040bbd8  mov     rdx, rdi; struct StringPtr *
0x10040bbdb  mov     rcx, rbp; this
0x10040bbde  call    ?FillAttributeValue@YReader@@AEAAXPEAUStringPtr@@00@Z; YReader::FillAttributeValue(StringPtr *,StringPtr *,StringPtr *)
0x10040bbe3  mov     qword ptr [rbx+88h], 0
0x10040bbee  jmp     short loc_10040BC44
0x10040bbf0  mov     eax, [rax+68h]
0x10040bbf3  lea     rcx, [rbp+1A0h]; this
0x10040bbfa  sub     eax, [r14+8]
0x10040bbfe  add     [rdi+8], eax
0x10040bc01  mov     r8d, [rdi+8]
0x10040bc05  mov     rdx, [rdi]; void *
0x10040bc08  add     r8d, r8d; unsigned int
0x10040bc0b  call    ?ReallocData@BlockAlloc@@QEAAPEAXPEAXK@Z; BlockAlloc::ReallocData(void *,ulong)
0x10040bc10  mov     [rsi], rax
0x10040bc13  mov     [rdi], rax
0x10040bc16  mov     ecx, [rsi+8]
0x10040bc19  mov     rax, [rsi]
0x10040bc1c  mov     edx, [rbx+68h]
0x10040bc1f  lea     r9, [rax+rcx*2]
0x10040bc23  mov     eax, [rdi+8]
0x10040bc26  sub     eax, ecx
0x10040bc28  cmp     eax, edx
0x10040bc2a  jb      short loc_10040BC6A
0x10040bc2c  mov     r8d, edx
0x10040bc2f  mov     rcx, r9; void *
0x10040bc32  mov     rdx, [rbx+60h]; Src
0x10040bc36  add     r8, r8; Size
0x10040bc39  call    memmove
0x10040bc3e  mov     eax, [rbx+68h]
0x10040bc41  add     [rsi+8], eax
0x10040bc44  mov     rbx, [rsp+28h+arg_0]
0x10040bc49  mov     rbp, [rsp+28h+arg_8]
0x10040bc4e  mov     rsi, [rsp+28h+arg_10]
0x10040bc53  mov     rdi, [rsp+28h+arg_18]
0x10040bc58  add     rsp, 20h
0x10040bc5c  pop     r14
0x10040bc5e  retn
0x10040bc5f  mov     ecx, 0C00CEE45h; int
0x10040bc64  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040bc69  int     3; Trap to Debugger
0x10040bc6a  mov     ecx, 80004005h; int
0x10040bc6f  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
