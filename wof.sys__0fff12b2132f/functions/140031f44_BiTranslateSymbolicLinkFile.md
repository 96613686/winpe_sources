# BiTranslateSymbolicLinkFile

- ea: `0x140031f44`
- end: `0x1400320b9`
- name: `BiTranslateSymbolicLinkFile`
- size: `373`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x140031500`

## callees

- `0x14000da0d`
- `0x1400116c0`
- `0x140031d8c`
- `0x140031f44`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140032013`
- `ntoskrnl!ExAllocatePool2` at `0x140032013`
- `ntoskrnl!wcsrchr` at `0x140031f91`
- `ntoskrnl!wcsrchr` at `0x140031f91`

## pseudocode

```c
__int64 __fastcall BiTranslateSymbolicLinkFile(wchar_t *SourceString, wchar_t **a2)
{
  _WORD *v4; // rdi
  wchar_t *v5; // rsi
  wchar_t *v6; // r14
  char v7; // bp
  wchar_t *v8; // rax
  wchar_t *v9; // rbx
  NTSTATUS v10; // eax
  __int64 v11; // rax
  size_t v12; // r14
  __int64 v13; // rax
  wchar_t *Pool2; // rax
  wchar_t *v15; // r13
  unsigned int v16; // ebx
  unsigned int Size; // [rsp+60h] [rbp+8h]
  void *Src; // [rsp+70h] [rbp+18h] BYREF

  Src = 0;
  v4 = 0;
  if ( SourceString && a2 )
  {
    *a2 = 0;
    v5 = SourceString;
    v6 = 0;
    v7 = 0;
    while ( 1 )
    {
      v8 = wcsrchr(v5, 0x5Cu);
      v9 = v8;
      if ( v6 )
        *v6 = 92;
      if ( !v8 )
        break;
      *v8 = 0;
      v10 = BiTranslateSymbolicLink(v5, (PWSTR *)&Src);
      v4 = Src;
      if ( v10 >= 0 )
      {
        *v9 = 92;
        v11 = -1;
        do
          ++v11;
        while ( v4[v11] );
        v12 = (unsigned int)(2 * v11);
        v13 = -1;
        do
          ++v13;
        while ( v9[v13] );
        Size = 2 * v13 + 2;
        Pool2 = (wchar_t *)ExAllocatePool2(258, (unsigned int)v12 + Size, 1262764866);
        *a2 = Pool2;
        v15 = Pool2;
        if ( !Pool2 )
        {
          v16 = -1073741801;
          goto LABEL_20;
        }
        v7 = 1;
        memmove(Pool2, v4, v12);
        memmove((char *)v15 + v12, v9, Size);
        if ( v5 != SourceString )
          ExFreePoolWithTag_0(v5, 0x4B444342u);
        v5 = *a2;
        v9 = (wchar_t *)((char *)*a2 + v12);
        *v9 = 0;
      }
      v6 = v9;
    }
    v16 = v7 == 0 ? 0xC0000001 : 0;
  }
  else
  {
    v16 = -1073741811;
  }
LABEL_20:
  if ( v4 )
    ExFreePoolWithTag_0(v4, 0x4B444342u);
  return v16;
}

```

## disassembly

```asm
0x140031f44  mov     [rsp+arg_8], rbx
0x140031f49  push    rbp
0x140031f4a  push    rsi
0x140031f4b  push    rdi
0x140031f4c  push    r12
0x140031f4e  push    r13
0x140031f50  push    r14
0x140031f52  push    r15
0x140031f54  sub     rsp, 20h
0x140031f58  xor     r13d, r13d
0x140031f5b  mov     r15, rdx
0x140031f5e  mov     [rsp+58h+Src], r13
0x140031f63  mov     r12, rcx
0x140031f66  mov     edi, r13d
0x140031f69  test    rcx, rcx
0x140031f6c  jz      loc_14003208A
0x140031f72  test    rdx, rdx
0x140031f75  jz      loc_14003208A
0x140031f7b  mov     [rdx], r13
0x140031f7e  mov     rsi, rcx
0x140031f81  mov     r14d, r13d
0x140031f84  mov     bpl, r13b
0x140031f87  mov     eax, 5Ch ; '\'
0x140031f8c  mov     rcx, rsi; Str
0x140031f8f  mov     edx, eax; Ch
0x140031f91  call    cs:__imp_wcsrchr
0x140031f98  nop     dword ptr [rax+rax+00h]
0x140031f9d  mov     rbx, rax
0x140031fa0  test    r14, r14
0x140031fa3  jz      short loc_140031FAB
0x140031fa5  mov     word ptr [r14], 5Ch ; '\'
0x140031fab  test    rbx, rbx
0x140031fae  jz      loc_14003207B
0x140031fb4  lea     rdx, [rsp+58h+Src]
0x140031fb9  mov     [rax], r13w
0x140031fbd  mov     rcx, rsi; SourceString
0x140031fc0  call    BiTranslateSymbolicLink
0x140031fc5  mov     rdi, [rsp+58h+Src]
0x140031fca  test    eax, eax
0x140031fcc  js      loc_14003206C
0x140031fd2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140031fd6  mov     word ptr [rbx], 5Ch ; '\'
0x140031fdb  mov     rax, rcx
0x140031fde  inc     rax
0x140031fe1  cmp     [rdi+rax*2], r13w
0x140031fe6  jnz     short loc_140031FDE
0x140031fe8  lea     r14d, [rax+rax]
0x140031fec  mov     rax, rcx
0x140031fef  inc     rax
0x140031ff2  cmp     [rbx+rax*2], r13w
0x140031ff7  jnz     short loc_140031FEF
0x140031ff9  lea     eax, ds:2[rax*2]
0x140032000  mov     ecx, 102h
0x140032005  lea     edx, [r14+rax]
0x140032009  mov     dword ptr [rsp+58h+Size], eax
0x14003200d  mov     r8d, 4B444342h
0x140032013  call    cs:__imp_ExAllocatePool2
0x14003201a  nop     dword ptr [rax+rax+00h]
0x14003201f  mov     [r15], rax
0x140032022  mov     r13, rax
0x140032025  test    rax, rax
0x140032028  jz      short loc_140032074
0x14003202a  mov     r8, r14; Size
0x14003202d  mov     rdx, rdi; Src
0x140032030  mov     rcx, rax; void *
0x140032033  mov     bpl, 1
0x140032036  call    memmove
0x14003203b  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x140032040  lea     rcx, [r14+r13]; void *
0x140032044  mov     rdx, rbx; Src
0x140032047  call    memmove
0x14003204c  cmp     rsi, r12
0x14003204f  jz      short loc_14003205E
0x140032051  mov     edx, 4B444342h; Tag
0x140032056  mov     rcx, rsi; P
0x140032059  call    ExFreePoolWithTag_0
0x14003205e  mov     rsi, [r15]
0x140032061  xor     r13d, r13d
0x140032064  lea     rbx, [rsi+r14]
0x140032068  mov     [rbx], r13w
0x14003206c  mov     r14, rbx
0x14003206f  jmp     loc_140031F87
0x140032074  mov     ebx, 0C0000017h
0x140032079  jmp     short loc_14003208F
0x14003207b  neg     bpl
0x14003207e  sbb     ebx, ebx
0x140032080  not     ebx
0x140032082  and     ebx, 0C0000001h
0x140032088  jmp     short loc_14003208F
0x14003208a  mov     ebx, 0C000000Dh
0x14003208f  test    rdi, rdi
0x140032092  jz      short loc_1400320A1
0x140032094  mov     edx, 4B444342h; Tag
0x140032099  mov     rcx, rdi; P
0x14003209c  call    ExFreePoolWithTag_0
0x1400320a1  mov     eax, ebx
0x1400320a3  mov     rbx, [rsp+58h+arg_8]
0x1400320a8  add     rsp, 20h
0x1400320ac  pop     r15
0x1400320ae  pop     r14
0x1400320b0  pop     r13
0x1400320b2  pop     r12
0x1400320b4  pop     rdi
0x1400320b5  pop     rsi
0x1400320b6  pop     rbp
0x1400320b7  retn
```
