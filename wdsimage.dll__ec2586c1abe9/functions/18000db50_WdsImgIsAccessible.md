# WdsImgIsAccessible

- ea: `0x18000db50`
- end: `0x18000dbc0`
- name: `WdsImgIsAccessible`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18000d780`
- `0x18000da10`
- `0x18000db50`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x18000db92`
- `KERNEL32!GetFileAttributesW` at `0x18000db92`

## pseudocode

```c
__int64 __fastcall WdsImgIsAccessible(__int64 a1, _DWORD *a2, __int64 a3)
{
  int v3; // ebx
  unsigned int Path; // edi
  __int64 v6; // rdx
  __int64 v7; // r8
  LPCWSTR lpFileName; // [rsp+30h] [rbp+8h] BYREF

  v3 = 0;
  lpFileName = 0;
  if ( a1 && a2 )
  {
    Path = WdsImgGetPath(a1, &lpFileName, a3);
    if ( (int)ElValidateHr_6(Path, v6, v7, 126) >= 0 )
    {
      LOBYTE(v3) = GetFileAttributesW(lpFileName) != -1;
      *a2 = v3;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return Path;
}

```

## disassembly

```asm
0x18000db50  mov     rax, rsp
0x18000db53  mov     [rax+10h], rbx
0x18000db57  mov     [rax+18h], rsi
0x18000db5b  push    rdi
0x18000db5c  sub     rsp, 20h
0x18000db60  xor     ebx, ebx
0x18000db62  mov     rsi, rdx
0x18000db65  mov     [rax+8], rbx
0x18000db69  test    rcx, rcx
0x18000db6c  jz      short loc_18000DBA8
0x18000db6e  test    rdx, rdx
0x18000db71  jz      short loc_18000DBA8
0x18000db73  lea     rdx, [rax+8]
0x18000db77  call    WdsImgGetPath
0x18000db7c  lea     r9d, [rbx+7Eh]
0x18000db80  mov     ecx, eax
0x18000db82  mov     edi, eax
0x18000db84  call    ElValidateHr_6
0x18000db89  test    eax, eax
0x18000db8b  js      short loc_18000DBAD
0x18000db8d  mov     rcx, [rsp+28h+lpFileName]; lpFileName
0x18000db92  call    cs:__imp_GetFileAttributesW
0x18000db99  nop     dword ptr [rax+rax+00h]
0x18000db9e  cmp     eax, 0FFFFFFFFh
0x18000dba1  setnz   bl
0x18000dba4  mov     [rsi], ebx
0x18000dba6  jmp     short loc_18000DBAD
0x18000dba8  mov     edi, 80070057h
0x18000dbad  mov     rbx, [rsp+28h+arg_8]
0x18000dbb2  mov     eax, edi
0x18000dbb4  mov     rsi, [rsp+28h+arg_10]
0x18000dbb9  add     rsp, 20h
0x18000dbbd  pop     rdi
0x18000dbbe  retn
```
