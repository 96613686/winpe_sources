# ArgpReadString(ushort const *,TYPED_ARGUMENT<ushort *> *)

- ea: `0x14003eb98`
- end: `0x14003ecab`
- name: `?ArgpReadString@@YAJPEBGPEAV?$TYPED_ARGUMENT@PEAG@@@Z`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14003e608`

## callees

- `0x140002bd4`
- `0x14003b898`
- `0x14003dd0c`
- `0x14003eb98`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14003ec52`
- `msvcrt!_wcsicmp` at `0x14003ec52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003ec82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003ec82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003ebd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003ec74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003ebd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003ec74`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003ebe1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003ebe1`

## pseudocode

```c
__int64 __fastcall ArgpReadString(const unsigned __int16 *a1, __int64 a2)
{
  unsigned __int16 *v3; // rax
  unsigned int v4; // ebx
  HANDLE ProcessHeap; // rax
  wchar_t *v6; // rax
  wchar_t *v7; // rsi
  __int64 v8; // rcx
  wchar_t **v9; // r8
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  wchar_t *i; // rcx
  wchar_t *v13; // rax
  HANDLE v14; // rax

  v3 = ArgDuplicateString(a1);
  *(_QWORD *)(a2 + 128) = v3;
  if ( !v3 )
    return (unsigned int)-2147024882;
  if ( (*(_BYTE *)(a2 + 44) & 0x20) != 0 )
  {
    ProcessHeap = GetProcessHeap();
    v6 = (wchar_t *)HeapAlloc(ProcessHeap, 0, 0x800u);
    v7 = v6;
    if ( !v6 )
      return (unsigned int)-2147024882;
    *v6 = 0;
    v8 = 2147483646;
    v9 = *(wchar_t ***)(a2 + 64);
    v10 = 1024;
    do
    {
      if ( !v8 )
        break;
      if ( !*(_WORD *)v9 )
        break;
      *v6 = *(_WORD *)v9;
      v9 = (wchar_t **)((char *)v9 + 2);
      ++v6;
      --v8;
      --v10;
    }
    while ( v10 );
    v11 = v6 - 1;
    if ( v10 )
      v11 = v6;
    *v11 = 0;
    v4 = v10 == 0 ? 0x8007007A : 0;
    if ( v10 )
    {
      for ( i = v7; ; i = 0 )
      {
        v13 = wcstok_mvcrt_legacy_two_parameter_form(i, L"|", v9);
        if ( !v13 )
          break;
        if ( !_wcsicmp(*(const wchar_t **)(a2 + 128), v13) )
          goto LABEL_17;
      }
      v4 = -2147024809;
    }
LABEL_17:
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v7);
  }
  else
  {
    v4 = 0;
    if ( *(char *)(a2 + 44) < 0 )
      return (unsigned int)ArgExpandFiles((unsigned __int16 **)(a2 + 128), 0);
  }
  return v4;
}

```

## disassembly

```asm
0x14003eb98  push    rbx
0x14003eb9a  push    rbp
0x14003eb9b  push    rsi
0x14003eb9c  push    rdi
0x14003eb9d  push    r14
0x14003eb9f  sub     rsp, 20h
0x14003eba3  mov     rdi, rdx
0x14003eba6  call    ?ArgDuplicateString@@YAPEAGPEBG@Z; ArgDuplicateString(ushort const *)
0x14003ebab  xor     ebp, ebp
0x14003ebad  lea     r14, [rdi+80h]
0x14003ebb4  mov     [r14], rax
0x14003ebb7  test    rax, rax
0x14003ebba  jnz     short loc_14003EBC6
0x14003ebbc  mov     ebx, 8007000Eh
0x14003ebc1  jmp     loc_14003EC9E
0x14003ebc6  test    byte ptr [rdi+2Ch], 20h
0x14003ebca  jz      loc_14003EC8A
0x14003ebd0  call    cs:__imp_GetProcessHeap
0x14003ebd6  xor     edx, edx; dwFlags
0x14003ebd8  mov     r8d, 800h; dwBytes
0x14003ebde  mov     rcx, rax; hHeap
0x14003ebe1  call    cs:__imp_HeapAlloc
0x14003ebe7  mov     rsi, rax
0x14003ebea  test    rax, rax
0x14003ebed  jz      short loc_14003EBBC
0x14003ebef  mov     [rax], bp
0x14003ebf2  mov     ecx, 7FFFFFFEh
0x14003ebf7  mov     r8, [rdi+40h]
0x14003ebfb  mov     edx, 400h
0x14003ec00  test    rcx, rcx
0x14003ec03  jz      short loc_14003EC24
0x14003ec05  movzx   r9d, word ptr [r8]
0x14003ec09  test    r9w, r9w
0x14003ec0d  jz      short loc_14003EC24
0x14003ec0f  mov     [rax], r9w
0x14003ec13  add     r8, 2
0x14003ec17  add     rax, 2
0x14003ec1b  dec     rcx
0x14003ec1e  sub     rdx, 1
0x14003ec22  jnz     short loc_14003EC00
0x14003ec24  test    rdx, rdx
0x14003ec27  lea     rcx, [rax-2]
0x14003ec2b  cmovnz  rcx, rax
0x14003ec2f  mov     rax, rdx
0x14003ec32  neg     rax
0x14003ec35  sbb     ebx, ebx
0x14003ec37  not     ebx
0x14003ec39  mov     [rcx], bp
0x14003ec3c  and     ebx, 8007007Ah
0x14003ec42  test    rdx, rdx
0x14003ec45  jz      short loc_14003EC74
0x14003ec47  mov     rcx, rsi
0x14003ec4a  jmp     short loc_14003EC5E
0x14003ec4c  mov     rcx, [r14]; String1
0x14003ec4f  mov     rdx, rax; String2
0x14003ec52  call    cs:__imp__wcsicmp
0x14003ec58  test    eax, eax
0x14003ec5a  jz      short loc_14003EC74
0x14003ec5c  xor     ecx, ecx; String
0x14003ec5e  lea     rdx, asc_140045C3C; "|"
0x14003ec65  call    wcstok_mvcrt_legacy_two_parameter_form
0x14003ec6a  test    rax, rax
0x14003ec6d  jnz     short loc_14003EC4C
0x14003ec6f  mov     ebx, 80070057h
0x14003ec74  call    cs:__imp_GetProcessHeap
0x14003ec7a  mov     r8, rsi; lpMem
0x14003ec7d  xor     edx, edx; dwFlags
0x14003ec7f  mov     rcx, rax; hHeap
0x14003ec82  call    cs:__imp_HeapFree
0x14003ec88  jmp     short loc_14003EC9E
0x14003ec8a  test    byte ptr [rdi+2Ch], 80h
0x14003ec8e  mov     ebx, ebp
0x14003ec90  jz      short loc_14003EC9E
0x14003ec92  xor     edx, edx; int
0x14003ec94  mov     rcx, r14; unsigned __int16 **
0x14003ec97  call    ?ArgExpandFiles@@YAJPEAPEAGH@Z; ArgExpandFiles(ushort * *,int)
0x14003ec9c  mov     ebx, eax
0x14003ec9e  mov     eax, ebx
0x14003eca0  add     rsp, 20h
0x14003eca4  pop     r14
0x14003eca6  pop     rdi
0x14003eca7  pop     rsi
0x14003eca8  pop     rbp
0x14003eca9  pop     rbx
0x14003ecaa  retn
```
