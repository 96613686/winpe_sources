# UnmapDosDrive(_UNICODE_STRING const *)

- ea: `0x140004260`
- end: `0x140004328`
- name: `?UnmapDosDrive@@YAXPEBU_UNICODE_STRING@@@Z`
- size: `200`
- prototype: `void __fastcall(PCUNICODE_STRING String1)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001f410`
- `0x14001f6c0`

## callees

- `0x140003944`
- `0x140004260`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400042d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400042d4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400042a2`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400042a2`
- `FLTMGR!FltReleasePushLockEx` at `0x1400042f1`
- `FLTMGR!FltReleasePushLockEx` at `0x1400042f1`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14000427c`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14000427c`

## string_xrefs

- `0x140004306`: `Successfully removed mapping: %wZ <==> %c:`

## pseudocode

```c
void __fastcall UnmapDosDrive(PCUNICODE_STRING String1)
{
  unsigned __int8 v2; // bl
  __int64 v3; // rdi
  unsigned __int64 *v4; // rbp
  unsigned __int16 v5; // bx
  void *v6; // rcx

  FltAcquirePushLockExclusiveEx(&qword_140019650, 0);
  v2 = 0;
  while ( 1 )
  {
    v3 = 2LL * v2;
    v4 = &qword_140019650 + 2 * v2;
    if ( RtlEqualUnicodeString(String1, (PCUNICODE_STRING)(v4 + 1), 1u) )
      break;
    if ( ++v2 >= 0x1Au )
    {
      v5 = 0;
      goto LABEL_8;
    }
  }
  v6 = (void *)*(&qword_140019650 + 2 * v2 + 2);
  v5 = v2 + 65;
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0x6E6D7377u);
    *(&qword_140019650 + v3 + 2) = 0;
  }
  *(_OWORD *)(v4 + 1) = 0;
LABEL_8:
  FltReleasePushLockEx(&qword_140019650, 0);
  if ( v5 )
    WriteLogMessage(1, L"Successfully removed mapping: %wZ <==> %c:", String1, v5);
}

```

## disassembly

```asm
0x140004260  push    rbx
0x140004262  push    rbp
0x140004263  push    rsi
0x140004264  push    rdi
0x140004265  push    r14
0x140004267  push    r15
0x140004269  sub     rsp, 28h
0x14000426d  mov     rsi, rcx
0x140004270  lea     r15, qword_140019650
0x140004277  mov     rcx, r15
0x14000427a  xor     edx, edx
0x14000427c  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140004283  nop     dword ptr [rax+rax+00h]
0x140004288  xor     r14d, r14d
0x14000428b  mov     bl, r14b
0x14000428e  movzx   edi, bl
0x140004291  mov     r8b, 1; CaseInSensitive
0x140004294  add     rdi, rdi
0x140004297  mov     rcx, rsi; String1
0x14000429a  lea     rbp, [r15+rdi*8]
0x14000429e  lea     rdx, [rbp+8]; String2
0x1400042a2  call    cs:__imp_RtlEqualUnicodeString
0x1400042a9  nop     dword ptr [rax+rax+00h]
0x1400042ae  test    al, al
0x1400042b0  jnz     short loc_1400042BE
0x1400042b2  inc     bl
0x1400042b4  cmp     bl, 1Ah
0x1400042b7  jb      short loc_14000428E
0x1400042b9  mov     ebx, r14d
0x1400042bc  jmp     short loc_1400042EC
0x1400042be  mov     rcx, [r15+rdi*8+10h]; P
0x1400042c3  movzx   ebx, bl
0x1400042c6  add     bx, 41h ; 'A'
0x1400042ca  test    rcx, rcx
0x1400042cd  jz      short loc_1400042E5
0x1400042cf  mov     edx, 6E6D7377h; Tag
0x1400042d4  call    cs:__imp_ExFreePoolWithTag
0x1400042db  nop     dword ptr [rax+rax+00h]
0x1400042e0  mov     [r15+rdi*8+10h], r14
0x1400042e5  xorps   xmm0, xmm0
0x1400042e8  movups  xmmword ptr [rbp+8], xmm0
0x1400042ec  xor     edx, edx
0x1400042ee  mov     rcx, r15
0x1400042f1  call    cs:__imp_FltReleasePushLockEx
0x1400042f8  nop     dword ptr [rax+rax+00h]
0x1400042fd  test    bx, bx
0x140004300  jz      short loc_14000431A
0x140004302  movzx   r9d, bx
0x140004306  lea     rdx, aSuccessfullyRe; "Successfully removed mapping: %wZ <==> "...
0x14000430d  mov     r8, rsi
0x140004310  mov     ecx, 1
0x140004315  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14000431a  add     rsp, 28h
0x14000431e  pop     r15
0x140004320  pop     r14
0x140004322  pop     rdi
0x140004323  pop     rsi
0x140004324  pop     rbp
0x140004325  pop     rbx
0x140004326  retn
```
