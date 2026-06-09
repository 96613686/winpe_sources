# MakeMemStreamCopyOfStream(IStream *,IStream * *)

- ea: `0x18000ed0c`
- end: `0x18000edc5`
- name: `?MakeMemStreamCopyOfStream@@YAJPEAUIStream@@PEAPEAU1@@Z`
- size: `185`
- prototype: `__int64 __fastcall(struct IStream *pstmFrom, struct IStream **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800104d0`
- `0x180011e88`

## callees

- `0x18000ba14`
- `0x18000ed0c`
- `0x18001f010`

## import_xrefs

- `SHCORE!IStream_Size` at `0x18000ed34`
- `SHCORE!IStream_Size` at `0x18000ed34`
- `SHCORE!IStream_Reset` at `0x18000ed86`
- `SHCORE!IStream_Reset` at `0x18000ed86`
- `SHCORE!IStream_Copy` at `0x18000ed77`
- `SHCORE!IStream_Copy` at `0x18000ed77`

## pseudocode

```c
__int64 __fastcall MakeMemStreamCopyOfStream(struct IStream *pstmFrom, struct IStream **a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  HRESULT v6; // ebx
  IStream *v7; // rdi
  ULARGE_INTEGER pui; // [rsp+48h] [rbp+10h] BYREF
  IStream *pstmTo; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  pui.QuadPart = 0;
  v6 = IStream_Size(pstmFrom, &pui);
  if ( v6 >= 0 )
  {
    if ( pui.HighPart )
    {
      return (unsigned int)-2147024673;
    }
    else
    {
      pstmTo = 0;
      v6 = SHCreateMemoryStream(v5, v4, &pstmTo);
      if ( v6 >= 0 )
      {
        v7 = pstmTo;
        v6 = IStream_Copy(pstmFrom, pstmTo, pui.LowPart);
        if ( v6 >= 0 )
        {
          IStream_Reset(v7);
          v6 = (**(__int64 (__fastcall ***)(IStream *, GUID *, struct IStream **))v7)(
                 v7,
                 &GUID_0000000c_0000_0000_c000_000000000046,
                 a2);
        }
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)v7 + 16LL))(v7);
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000ed0c  mov     [rsp+arg_0], rbx
0x18000ed11  push    rsi
0x18000ed12  push    rdi
0x18000ed13  push    r14
0x18000ed15  sub     rsp, 20h
0x18000ed19  mov     r14, rdx
0x18000ed1c  mov     qword ptr [rdx], 0
0x18000ed23  lea     rdx, [rsp+38h+pui]; pui
0x18000ed28  mov     qword ptr [rsp+38h+pui], 0
0x18000ed31  mov     rsi, rcx
0x18000ed34  call    cs:__imp_IStream_Size
0x18000ed3a  mov     ebx, eax
0x18000ed3c  test    eax, eax
0x18000ed3e  js      short loc_18000EDB5
0x18000ed40  cmp     dword ptr [rsp+38h+pui+4], 0
0x18000ed45  jz      short loc_18000ED4E
0x18000ed47  mov     ebx, 800700DFh
0x18000ed4c  jmp     short loc_18000EDB5
0x18000ed4e  lea     r8, [rsp+38h+pstmTo]
0x18000ed53  mov     [rsp+38h+pstmTo], 0
0x18000ed5c  call    SHCreateMemoryStream
0x18000ed61  mov     ebx, eax
0x18000ed63  test    eax, eax
0x18000ed65  js      short loc_18000EDB5
0x18000ed67  mov     rdi, [rsp+38h+pstmTo]
0x18000ed6c  mov     rcx, rsi; pstmFrom
0x18000ed6f  mov     r8d, dword ptr [rsp+38h+pui]; cb
0x18000ed74  mov     rdx, rdi; pstmTo
0x18000ed77  call    cs:__imp_IStream_Copy
0x18000ed7d  mov     ebx, eax
0x18000ed7f  test    eax, eax
0x18000ed81  js      short loc_18000EDA6
0x18000ed83  mov     rcx, rdi; pstm
0x18000ed86  call    cs:__imp_IStream_Reset
0x18000ed8c  mov     rax, [rdi]
0x18000ed8f  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x18000ed96  mov     r8, r14
0x18000ed99  mov     rcx, rdi
0x18000ed9c  mov     rax, [rax]
0x18000ed9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eda4  mov     ebx, eax
0x18000eda6  mov     rax, [rdi]
0x18000eda9  mov     rcx, rdi
0x18000edac  mov     rax, [rax+10h]
0x18000edb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edb5  mov     eax, ebx
0x18000edb7  mov     rbx, [rsp+38h+arg_0]
0x18000edbc  add     rsp, 20h
0x18000edc0  pop     r14
0x18000edc2  pop     rdi
0x18000edc3  pop     rsi
0x18000edc4  retn
```
