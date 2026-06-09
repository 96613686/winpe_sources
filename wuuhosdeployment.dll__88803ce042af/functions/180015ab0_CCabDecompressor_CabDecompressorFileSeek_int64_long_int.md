# CCabDecompressor::CabDecompressorFileSeek(__int64,long,int)

- ea: `0x180015ab0`
- end: `0x180015b5e`
- name: `?CabDecompressorFileSeek@CCabDecompressor@@CAJ_JJH@Z`
- size: `174`
- prototype: `int __cdecl(INT_PTR hf, int dist, int seektype)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000956c`
- `0x180015ab0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b17`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180015b0a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180015b0a`

## string_xrefs

- `0x180015b37`: `CabDecompressorFileSeek - SetFilePointer`

## pseudocode

```c
__int64 __fastcall CCabDecompressor::CabDecompressorFileSeek(INT_PTR hf, unsigned int dist, int seektype)
{
  int v3; // r8d
  DWORD v4; // r9d
  DWORD v5; // r9d
  DWORD v7; // ebx

  if ( seektype )
  {
    v3 = seektype - 1;
    if ( !v3 )
    {
      v4 = 1;
      goto LABEL_7;
    }
    if ( v3 == 1 )
    {
      v4 = 2;
      goto LABEL_7;
    }
  }
  v4 = 0;
LABEL_7:
  if ( !*(_DWORD *)(hf + 16) )
  {
    if ( v4 )
    {
      v5 = v4 - 1;
      if ( !v5 )
      {
        *(_DWORD *)(hf + 20) += dist;
        return *(unsigned int *)(hf + 20);
      }
      if ( v5 == 1 )
      {
        *(_DWORD *)(hf + 20) -= dist;
        return *(unsigned int *)(hf + 20);
      }
    }
    *(_DWORD *)(hf + 20) = dist;
    return dist;
  }
  v7 = SetFilePointer(*(HANDLE *)(hf + 8), dist, 0, v4);
  if ( v7 == -1 )
  {
    GetLastError();
    WUTrace(0, 0, 32, 3);
  }
  return v7;
}

```

## disassembly

```asm
0x180015ab0  push    rbx
0x180015ab2  sub     rsp, 30h
0x180015ab6  test    r8d, r8d
0x180015ab9  jz      short loc_180015AD5
0x180015abb  sub     r8d, 1
0x180015abf  jz      short loc_180015ACD
0x180015ac1  cmp     r8d, 1
0x180015ac5  jnz     short loc_180015AD5
0x180015ac7  lea     r9d, [r8+1]
0x180015acb  jmp     short loc_180015AD8
0x180015acd  mov     r9d, 1
0x180015ad3  jmp     short loc_180015AD8
0x180015ad5  xor     r9d, r9d; dwMoveMethod
0x180015ad8  cmp     dword ptr [rcx+10h], 0
0x180015adc  jnz     short loc_180015B03
0x180015ade  test    r9d, r9d
0x180015ae1  jz      short loc_180015AFC
0x180015ae3  sub     r9d, 1
0x180015ae7  jz      short loc_180015AF4
0x180015ae9  cmp     r9d, 1
0x180015aed  jnz     short loc_180015AFC
0x180015aef  sub     [rcx+14h], edx
0x180015af2  jmp     short loc_180015AF7
0x180015af4  add     [rcx+14h], edx
0x180015af7  mov     edx, [rcx+14h]; lDistanceToMove
0x180015afa  jmp     short loc_180015AFF
0x180015afc  mov     [rcx+14h], edx
0x180015aff  mov     eax, edx
0x180015b01  jmp     short loc_180015B58
0x180015b03  mov     rcx, [rcx+8]; hFile
0x180015b07  xor     r8d, r8d; lpDistanceToMoveHigh
0x180015b0a  call    cs:__imp_SetFilePointer
0x180015b10  mov     ebx, eax
0x180015b12  cmp     eax, 0FFFFFFFFh
0x180015b15  jnz     short loc_180015B56
0x180015b17  call    cs:__imp_GetLastError
0x180015b1d  movzx   ecx, ax
0x180015b20  or      ecx, 80070000h
0x180015b26  test    eax, eax
0x180015b28  cmovle  ecx, eax
0x180015b2b  mov     eax, 8000FFFFh
0x180015b30  test    ecx, ecx
0x180015b32  cmovns  ecx, eax
0x180015b35  xor     edx, edx
0x180015b37  lea     rax, aCabdecompresso_4; "CabDecompressorFileSeek - SetFilePointe"...
0x180015b3e  mov     [rsp+38h+var_10], rax
0x180015b43  mov     [rsp+38h+var_18], ecx
0x180015b47  xor     ecx, ecx
0x180015b49  lea     r9d, [rdx+3]
0x180015b4d  lea     r8d, [rdx+20h]
0x180015b51  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180015b56  mov     eax, ebx
0x180015b58  add     rsp, 30h
0x180015b5c  pop     rbx
0x180015b5d  retn
```
