# CDesktopUpgradePropertyBag::_NewStreamFromOld(IStream *)

- ea: `0x180029d9c`
- end: `0x180029e9e`
- name: `?_NewStreamFromOld@CDesktopUpgradePropertyBag@@AEAAPEAUIStream@@PEAU2@@Z`
- size: `258`
- prototype: `struct IStream *(CDesktopUpgradePropertyBag *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180029800`

## callees

- `0x180012550`
- `0x180029d9c`
- `0x180037010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180029e1a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180029e1a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180029dce`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180029dce`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180029e6d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180029e6d`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180029e28`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180029e28`

## pseudocode

```c
struct IStream *__fastcall CDesktopUpgradePropertyBag::_NewStreamFromOld(
        CDesktopUpgradePropertyBag *this,
        struct IStream *a2)
{
  IStream *v3; // rbx
  __int64 v4; // rdx
  ULARGE_INTEGER pui; // [rsp+30h] [rbp-28h] BYREF
  __int128 pv; // [rsp+38h] [rbp-20h] BYREF

  v3 = 0;
  pv = 0;
  if ( IStream_Read(a2, &pv, 0x10u) >= 0
    && (_WORD)pv == 28
    && (*(int (__fastcall **)(struct IStream *, __int64, __int64, _QWORD))(*(_QWORD *)a2 + 40LL))(
         a2,
         HIWORD(pv) - 16LL,
         1,
         0) >= 0 )
  {
    pui.QuadPart = 0;
    if ( IStream_Size(a2, &pui) >= 0 )
    {
      v3 = SHCreateMemStream(0, 0);
      if ( v3 )
      {
        v4 = *(_QWORD *)a2;
        pui.QuadPart -= HIWORD(pv);
        if ( (*(int (__fastcall **)(struct IStream *, IStream *, ULARGE_INTEGER, _QWORD, _QWORD))(v4 + 56))(
               a2,
               v3,
               pui,
               0,
               0) < 0 )
        {
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)v3 + 16LL))(v3);
          return 0;
        }
        else
        {
          IStream_Reset(v3);
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180029d9c  mov     [rsp+arg_0], rbx
0x180029da1  push    rdi
0x180029da2  sub     rsp, 50h
0x180029da6  mov     rax, cs:__security_cookie
0x180029dad  xor     rax, rsp
0x180029db0  mov     [rsp+58h+var_10], rax
0x180029db5  mov     rdi, rdx
0x180029db8  xorps   xmm0, xmm0
0x180029dbb  xor     ebx, ebx
0x180029dbd  lea     rdx, [rsp+58h+pv]; pv
0x180029dc2  mov     rcx, rdi; pstm
0x180029dc5  movups  [rsp+58h+pv], xmm0
0x180029dca  lea     r8d, [rbx+10h]; cb
0x180029dce  call    cs:__imp_IStream_Read
0x180029dd4  test    eax, eax
0x180029dd6  js      loc_180029E83
0x180029ddc  lea     eax, [rbx+1Ch]
0x180029ddf  cmp     ax, word ptr [rsp+58h+pv]
0x180029de4  jnz     loc_180029E83
0x180029dea  mov     rax, [rdi]
0x180029ded  lea     r8d, [rbx+1]
0x180029df1  movzx   edx, word ptr [rsp+58h+pv+0Eh]
0x180029df6  xor     r9d, r9d
0x180029df9  sub     rdx, 10h
0x180029dfd  mov     rcx, rdi
0x180029e00  mov     rax, [rax+28h]
0x180029e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e09  test    eax, eax
0x180029e0b  js      short loc_180029E83
0x180029e0d  lea     rdx, [rsp+58h+pui]; pui
0x180029e12  mov     qword ptr [rsp+58h+pui], rbx
0x180029e17  mov     rcx, rdi; pstm
0x180029e1a  call    cs:__imp_IStream_Size
0x180029e20  test    eax, eax
0x180029e22  js      short loc_180029E83
0x180029e24  xor     edx, edx; cbInit
0x180029e26  xor     ecx, ecx; pInit
0x180029e28  call    cs:__imp_SHCreateMemStream
0x180029e2e  mov     rbx, rax
0x180029e31  test    rax, rax
0x180029e34  jz      short loc_180029E83
0x180029e36  movzx   edx, word ptr [rsp+58h+pv+0Eh]
0x180029e3b  xor     r9d, r9d
0x180029e3e  mov     r8, qword ptr [rsp+58h+pui]
0x180029e43  mov     rcx, rdi
0x180029e46  sub     r8, rdx
0x180029e49  mov     [rsp+58h+var_38], 0
0x180029e52  mov     rdx, [rdi]
0x180029e55  mov     qword ptr [rsp+58h+pui], r8
0x180029e5a  mov     rax, [rdx+38h]
0x180029e5e  mov     rdx, rbx
0x180029e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e66  mov     rcx, rbx; pstm
0x180029e69  test    eax, eax
0x180029e6b  js      short loc_180029E75
0x180029e6d  call    cs:__imp_IStream_Reset
0x180029e73  jmp     short loc_180029E83
0x180029e75  mov     rax, [rbx]
0x180029e78  mov     rax, [rax+10h]
0x180029e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e81  xor     ebx, ebx
0x180029e83  mov     rax, rbx
0x180029e86  mov     rcx, [rsp+58h+var_10]
0x180029e8b  xor     rcx, rsp; StackCookie
0x180029e8e  call    __security_check_cookie
0x180029e93  mov     rbx, [rsp+58h+arg_0]
0x180029e98  add     rsp, 50h
0x180029e9c  pop     rdi
0x180029e9d  retn
```
