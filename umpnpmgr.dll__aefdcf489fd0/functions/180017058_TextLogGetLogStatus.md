# TextLogGetLogStatus

- ea: `0x180017058`
- end: `0x1800170ea`
- name: `TextLogGetLogStatus`
- size: `146`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800027a0`
- `0x1800056d0`
- `0x18000b160`
- `0x18000b360`
- `0x1800177e0`

## callees

- `0x18000c650`
- `0x18000f210`
- `0x1800101d8`
- `0x180017058`
- `0x18001812c`

## pseudocode

```c
__int64 __fastcall TextLogGetLogStatus(__int64 a1)
{
  unsigned int v1; // ebx
  unsigned __int16 *v3; // rcx
  unsigned __int16 *FileTitle; // rax
  HANDLE KeyHandle[3]; // [rsp+30h] [rbp-18h] BYREF
  int v7; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v8; // [rsp+60h] [rbp+18h] BYREF
  __int64 v9; // [rsp+68h] [rbp+20h] BYREF

  v1 = 0;
  v8 = 0;
  KeyHandle[0] = 0;
  v7 = 0;
  if ( !(unsigned int)pSetupOpenKeyEx((void *)0xFFFFFFFF80000002LL, L"SYSTEM\\Setup\\SetupapiLogStatus", 1u, KeyHandle) )
  {
    v3 = *(unsigned __int16 **)(a1 + 16);
    LODWORD(v9) = 4;
    FileTitle = pSetupGetFileTitle(v3);
    if ( !(unsigned int)pSetupQueryValue(KeyHandle[0], FileTitle, &v7, &v8, (unsigned int *)&v9) && v7 == 4 )
      v1 = v8;
    pSetupCloseKey((unsigned int)KeyHandle[0]);
  }
  return v1;
}

```

## disassembly

```asm
0x180017058  mov     rax, rsp
0x18001705b  mov     [rax+8], rbx
0x18001705f  push    rdi
0x180017060  sub     rsp, 40h
0x180017064  xor     ebx, ebx
0x180017066  lea     r9, [rax-18h]
0x18001706a  mov     rdi, rcx
0x18001706d  mov     [rax+18h], ebx
0x180017070  lea     rdx, aSystemSetupSet_0; "SYSTEM\\Setup\\SetupapiLogStatus"
0x180017077  mov     [rax-18h], rbx
0x18001707b  mov     rcx, 0FFFFFFFF80000002h
0x180017082  mov     [rax+10h], ebx
0x180017085  lea     r8d, [rbx+1]
0x180017089  call    pSetupOpenKeyEx
0x18001708e  test    eax, eax
0x180017090  jnz     short loc_1800170DD
0x180017092  mov     rcx, [rdi+10h]
0x180017096  mov     dword ptr [rsp+48h+arg_18], 4
0x18001709e  call    pSetupGetFileTitle
0x1800170a3  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x1800170a8  lea     r9, [rsp+48h+arg_10]
0x1800170ad  mov     rdx, rax; SourceString
0x1800170b0  lea     r8, [rsp+48h+arg_8]
0x1800170b5  lea     rax, [rsp+48h+arg_18]
0x1800170ba  mov     [rsp+48h+var_28], rax; __int64
0x1800170bf  call    pSetupQueryValue
0x1800170c4  test    eax, eax
0x1800170c6  jnz     short loc_1800170D3
0x1800170c8  cmp     [rsp+48h+arg_8], 4
0x1800170cd  jnz     short loc_1800170D3
0x1800170cf  mov     ebx, [rsp+48h+arg_10]
0x1800170d3  mov     rcx, [rsp+48h+KeyHandle]
0x1800170d8  call    pSetupCloseKey
0x1800170dd  mov     eax, ebx
0x1800170df  mov     rbx, [rsp+48h+arg_0]
0x1800170e4  add     rsp, 40h
0x1800170e8  pop     rdi
0x1800170e9  retn
```
