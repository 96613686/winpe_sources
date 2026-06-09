# CEnumFORMATETC::AddElement(tagFORMATETC const *)

- ea: `0x180034b1c`
- end: `0x180034b8d`
- name: `?AddElement@CEnumFORMATETC@@QEAAJPEBUtagFORMATETC@@@Z`
- size: `113`
- prototype: `__int64 __fastcall(CEnumFORMATETC *__hidden this, const struct tagFORMATETC *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012020`

## callees

- `0x180011568`
- `0x180034b1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034b36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034b36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034b72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034b72`

## pseudocode

```c
__int64 __fastcall CEnumFORMATETC::AddElement(CEnumFORMATETC *this, const struct tagFORMATETC *a2)
{
  _OWORD *v4; // rax
  void *v5; // rbx

  v4 = CoTaskMemAlloc(0x20u);
  v5 = v4;
  if ( v4 )
  {
    *v4 = *(_OWORD *)&a2->cfFormat;
    v4[1] = *(_OWORD *)&a2->dwAspect;
    if ( DPA_InsertPtr(*((HDPA *)this + 3), 0x7FFFFFFF, v4) != -1 )
    {
      ++*((_DWORD *)this + 4);
      return 0;
    }
    CoTaskMemFree(v5);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180034b1c  mov     [rsp+arg_0], rbx
0x180034b21  mov     [rsp+arg_8], rsi
0x180034b26  push    rdi
0x180034b27  sub     rsp, 20h
0x180034b2b  mov     rdi, rcx
0x180034b2e  mov     rsi, rdx
0x180034b31  mov     ecx, 20h ; ' '; cb
0x180034b36  call    cs:__imp_CoTaskMemAlloc
0x180034b3c  mov     rbx, rax
0x180034b3f  test    rax, rax
0x180034b42  jz      short loc_180034B78
0x180034b44  movups  xmm0, xmmword ptr [rsi]
0x180034b47  mov     r8, rax; p
0x180034b4a  mov     edx, 7FFFFFFFh; i
0x180034b4f  movups  xmmword ptr [rax], xmm0
0x180034b52  movups  xmm1, xmmword ptr [rsi+10h]
0x180034b56  movups  xmmword ptr [rax+10h], xmm1
0x180034b5a  mov     rcx, [rdi+18h]; hdpa
0x180034b5e  call    DPA_InsertPtr
0x180034b63  cmp     eax, 0FFFFFFFFh
0x180034b66  jz      short loc_180034B6F
0x180034b68  inc     dword ptr [rdi+10h]
0x180034b6b  xor     eax, eax
0x180034b6d  jmp     short loc_180034B7D
0x180034b6f  mov     rcx, rbx; pv
0x180034b72  call    cs:__imp_CoTaskMemFree
0x180034b78  mov     eax, 8007000Eh
0x180034b7d  mov     rbx, [rsp+28h+arg_0]
0x180034b82  mov     rsi, [rsp+28h+arg_8]
0x180034b87  add     rsp, 20h
0x180034b8b  pop     rdi
0x180034b8c  retn
```
