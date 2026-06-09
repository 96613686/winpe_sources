# SetLogPath(_UNICODE_STRING const *,bool)

- ea: `0x140002ffc`
- end: `0x1400030b1`
- name: `?SetLogPath@@YAJPEBU_UNICODE_STRING@@_N@Z`
- size: `181`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x140001a94`
- `0x140002868`

## callees

- `0x140001748`
- `0x140002ffc`
- `0x14000e1d0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140003057`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003092`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003057`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003092`

## pseudocode

```c
__int64 __fastcall SetLogPath(const struct _UNICODE_STRING *a1, char a2)
{
  int NtPath; // ebx
  PVOID P[2]; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING v7; // [rsp+30h] [rbp-18h] BYREF

  *(_OWORD *)P = 0;
  v7 = 0;
  NtPath = GetNtPath(a1, (PUNICODE_STRING)P, &v7);
  if ( NtPath >= 0 )
  {
    if ( !a2 || (NtPath = PersistLogPath(a1), NtPath >= 0) )
    {
      if ( String2.Buffer )
        ExFreePoolWithTag(String2.Buffer, 0x6E6D7377u);
      String2 = *(UNICODE_STRING *)P;
      *(_OWORD *)P = 0;
    }
  }
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x6E6D7377u);
  return (unsigned int)NtPath;
}

```

## disassembly

```asm
0x140002ffc  mov     rax, rsp
0x140002fff  mov     [rax+8], rbx
0x140003003  mov     [rax+10h], rsi
0x140003007  push    rdi
0x140003008  sub     rsp, 40h
0x14000300c  mov     sil, dl
0x14000300f  lea     r8, [rax-18h]; struct _UNICODE_STRING *
0x140003013  xorps   xmm0, xmm0
0x140003016  lea     rdx, [rax-28h]; DestinationString
0x14000301a  xorps   xmm1, xmm1
0x14000301d  mov     rdi, rcx
0x140003020  movups  xmmword ptr [rax-28h], xmm0
0x140003024  movups  xmmword ptr [rax-18h], xmm1
0x140003028  call    ?GetNtPath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; GetNtPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x14000302d  mov     ebx, eax
0x14000302f  test    eax, eax
0x140003031  js      short loc_140003083
0x140003033  test    sil, sil
0x140003036  jz      short loc_140003046
0x140003038  mov     rcx, rdi; struct _UNICODE_STRING *
0x14000303b  call    ?PersistLogPath@@YAJPEBU_UNICODE_STRING@@@Z; PersistLogPath(_UNICODE_STRING const *)
0x140003040  mov     ebx, eax
0x140003042  test    eax, eax
0x140003044  js      short loc_140003083
0x140003046  mov     rcx, cs:String2.Buffer; P
0x14000304d  test    rcx, rcx
0x140003050  jz      short loc_140003063
0x140003052  mov     edx, 6E6D7377h; Tag
0x140003057  call    cs:__imp_ExFreePoolWithTag
0x14000305e  nop     dword ptr [rax+rax+00h]
0x140003063  mov     rax, [rsp+48h+P]
0x140003068  xorps   xmm0, xmm0
0x14000306b  mov     qword ptr cs:String2.Length, rax
0x140003072  mov     rax, [rsp+48h+P+8]
0x140003077  mov     cs:String2.Buffer, rax
0x14000307e  movups  xmmword ptr [rsp+48h+P], xmm0
0x140003083  mov     rcx, [rsp+48h+P+8]; P
0x140003088  test    rcx, rcx
0x14000308b  jz      short loc_14000309E
0x14000308d  mov     edx, 6E6D7377h; Tag
0x140003092  call    cs:__imp_ExFreePoolWithTag
0x140003099  nop     dword ptr [rax+rax+00h]
0x14000309e  mov     rsi, [rsp+48h+arg_8]
0x1400030a3  mov     eax, ebx
0x1400030a5  mov     rbx, [rsp+48h+arg_0]
0x1400030aa  add     rsp, 40h
0x1400030ae  pop     rdi
0x1400030af  retn
```
