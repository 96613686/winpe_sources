# RtlLoadStringOrError

- ea: `0x18000daf0`
- end: `0x18000dbad`
- name: `RtlLoadStringOrError`
- size: `189`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002724`
- `0x1800027f8`
- `0x1800046b0`
- `0x1800079d4`
- `0x18000c050`

## callees

- `0x18000daf0`
- `0x1800138ad`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18000db5e`
- `KERNELBASE!LocalAlloc` at `0x18000db5e`
- `ntdll!RtlFindMessage` at `0x18000db29`
- `ntdll!RtlFindMessage` at `0x18000db29`

## pseudocode

```c
HLOCAL __fastcall RtlLoadStringOrError(__int64 a1, ULONG a2, void *a3, _DWORD *a4)
{
  PMESSAGE_RESOURCE_ENTRY v6; // rsi
  __int64 v7; // rax
  int v8; // ebp
  HLOCAL v9; // rax
  HLOCAL v10; // rdi
  PMESSAGE_RESOURCE_ENTRY v12; // [rsp+70h] [rbp+8h] BYREF

  v12 = 0;
  if ( RtlFindMessage(ghModuleWin, 0xBu, 0, a2, &v12) < 0 )
    goto LABEL_7;
  v6 = v12;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)&v12->Text[2 * v7] );
  v8 = v7 - 2;
  v9 = LocalAlloc(0x40u, 2LL * ((int)v7 - 2 + 1));
  v10 = v9;
  if ( v9 )
  {
    memcpy_0(v9, v6->Text, 2LL * v8);
    if ( a4 )
      *a4 = 1;
  }
  else
  {
LABEL_7:
    v10 = a3;
    if ( a4 )
      *a4 = 0;
  }
  return v10;
}

```

## disassembly

```asm
0x18000daf0  mov     r11, rsp
0x18000daf3  mov     [r11+8], rcx
0x18000daf7  push    rbx
0x18000daf8  push    rbp
0x18000daf9  push    rsi
0x18000dafa  push    rdi
0x18000dafb  push    r14
0x18000dafd  push    r15
0x18000daff  sub     rsp, 38h
0x18000db03  mov     rcx, cs:ghModuleWin; BaseAddress
0x18000db0a  lea     rax, [r11+8]
0x18000db0e  xor     r15d, r15d
0x18000db11  mov     [r11-48h], rax
0x18000db15  mov     rbx, r9
0x18000db18  mov     [r11+8], r15
0x18000db1c  mov     r14, r8
0x18000db1f  mov     r9d, edx; MessageId
0x18000db22  xor     r8d, r8d; Language
0x18000db25  lea     edx, [r15+0Bh]; Type
0x18000db29  call    cs:__imp_RtlFindMessage
0x18000db30  nop     dword ptr [rax+rax+00h]
0x18000db35  test    eax, eax
0x18000db37  js      short loc_18000DB91
0x18000db39  mov     rsi, [rsp+68h+arg_0]
0x18000db3e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000db42  inc     rax
0x18000db45  cmp     [rsi+rax*2+4], r15w
0x18000db4b  jnz     short loc_18000DB42
0x18000db4d  lea     ebp, [rax-2]
0x18000db50  mov     ecx, 40h ; '@'; uFlags
0x18000db55  lea     eax, [rbp+1]
0x18000db58  movsxd  rdx, eax
0x18000db5b  add     rdx, rdx; uBytes
0x18000db5e  call    cs:__imp_LocalAlloc
0x18000db65  nop     dword ptr [rax+rax+00h]
0x18000db6a  mov     rdi, rax
0x18000db6d  test    rax, rax
0x18000db70  jz      short loc_18000DB91
0x18000db72  movsxd  r8, ebp
0x18000db75  lea     rdx, [rsi+4]; Src
0x18000db79  add     r8, r8; Size
0x18000db7c  mov     rcx, rax; void *
0x18000db7f  call    memcpy_0
0x18000db84  test    rbx, rbx
0x18000db87  jz      short loc_18000DB9C
0x18000db89  mov     dword ptr [rbx], 1
0x18000db8f  jmp     short loc_18000DB9C
0x18000db91  mov     rdi, r14
0x18000db94  test    rbx, rbx
0x18000db97  jz      short loc_18000DB9C
0x18000db99  mov     [rbx], r15d
0x18000db9c  mov     rax, rdi
0x18000db9f  add     rsp, 38h
0x18000dba3  pop     r15
0x18000dba5  pop     r14
0x18000dba7  pop     rdi
0x18000dba8  pop     rsi
0x18000dba9  pop     rbp
0x18000dbaa  pop     rbx
0x18000dbab  retn
```
