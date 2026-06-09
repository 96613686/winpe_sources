# AddUniqueIdentifierExtensionField(void *,ulong,ulong *)

- ea: `0x180057aa8`
- end: `0x180057b58`
- name: `?AddUniqueIdentifierExtensionField@@YAJPEAXKPEAK@Z`
- size: `176`
- prototype: `__int64 __fastcall(char *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800577b4`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x180057a60`
- `0x180057aa8`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x180057b0d`
- `bcrypt!BCryptGenRandom` at `0x180057b0d`

## string_xrefs

- `0x180057ad5`: `AddUniqueIdentifierExtensionField: Packet would be bigger than max NTS packet size. currentOffset: %d\n`
- `0x180057b30`: `AddUniqueIdentifierExtensionField: BCryptGenRandom failed with 0x%08X\n`

## pseudocode

```c
__int64 __fastcall AddUniqueIdentifierExtensionField(char *a1, unsigned int a2, unsigned int *a3)
{
  char *v6; // rbx
  NTSTATUS v7; // eax
  unsigned int v8; // ebx

  if ( (unsigned __int64)a2 + 36 < 0x500 )
  {
    v6 = &a1[a2];
    NtsExtFieldHeader::AddTypeAndLengthToExtensionField((u_short *)v6, 0x104u, 0x24u);
    v7 = BCryptGenRandom(0, (PUCHAR)v6 + 4, 0x20u, 2u);
    v8 = v7 | 0x10000000;
    if ( v7 >= 0 )
    {
      *a3 = a2 + 36;
      return 0;
    }
    else
    {
      if ( (unsigned __int8)FileLogAllowEntry(0) )
        FileLogAdd(L"AddUniqueIdentifierExtensionField: BCryptGenRandom failed with 0x%08X\n", v8);
      return v8;
    }
  }
  else
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(
        L"AddUniqueIdentifierExtensionField: Packet would be bigger than max NTS packet size. currentOffset: %d\n",
        a2);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180057aa8  mov     [rsp+arg_0], rbx
0x180057aad  mov     [rsp+arg_8], rsi
0x180057ab2  push    rdi
0x180057ab3  sub     rsp, 20h
0x180057ab7  mov     rsi, r8
0x180057aba  mov     edi, edx
0x180057abc  lea     rax, [rdi+24h]
0x180057ac0  cmp     rax, 500h
0x180057ac6  jb      short loc_180057AE8
0x180057ac8  xor     ecx, ecx
0x180057aca  call    FileLogAllowEntry
0x180057acf  test    al, al
0x180057ad1  jz      short loc_180057AE1
0x180057ad3  mov     edx, edi
0x180057ad5  lea     rcx, aAdduniqueident_0; "AddUniqueIdentifierExtensionField: Pack"...
0x180057adc  call    FileLogAdd
0x180057ae1  mov     eax, 8007000Eh
0x180057ae6  jmp     short loc_180057B47
0x180057ae8  lea     rbx, [rdi+rcx]
0x180057aec  mov     edx, 104h
0x180057af1  mov     r8d, 24h ; '$'
0x180057af7  mov     rcx, rbx
0x180057afa  call    ?AddTypeAndLengthToExtensionField@NtsExtFieldHeader@@QEAAXW4NtsExtFieldType@@K@Z; NtsExtFieldHeader::AddTypeAndLengthToExtensionField(NtsExtFieldType,ulong)
0x180057aff  lea     rdx, [rbx+4]; pbBuffer
0x180057b03  xor     ecx, ecx; hAlgorithm
0x180057b05  lea     r9d, [rcx+2]; dwFlags
0x180057b09  lea     r8d, [rcx+20h]; cbBuffer
0x180057b0d  call    cs:__imp_BCryptGenRandom
0x180057b14  nop     dword ptr [rax+rax+00h]
0x180057b19  mov     ebx, eax
0x180057b1b  or      ebx, 10000000h
0x180057b21  jge     short loc_180057B40
0x180057b23  xor     ecx, ecx
0x180057b25  call    FileLogAllowEntry
0x180057b2a  test    al, al
0x180057b2c  jz      short loc_180057B3C
0x180057b2e  mov     edx, ebx
0x180057b30  lea     rcx, aAdduniqueident; "AddUniqueIdentifierExtensionField: BCry"...
0x180057b37  call    FileLogAdd
0x180057b3c  mov     eax, ebx
0x180057b3e  jmp     short loc_180057B47
0x180057b40  lea     eax, [rdi+24h]
0x180057b43  mov     [rsi], eax
0x180057b45  xor     eax, eax
0x180057b47  mov     rbx, [rsp+28h+arg_0]
0x180057b4c  mov     rsi, [rsp+28h+arg_8]
0x180057b51  add     rsp, 20h
0x180057b55  pop     rdi
0x180057b56  retn
```
