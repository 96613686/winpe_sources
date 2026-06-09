# GetDllPath(void)

- ea: `0x140064038`
- end: `0x140064152`
- name: `?GetDllPath@@YAPEBGXZ`
- size: `282`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400657e8`

## callees

- `0x140045f20`
- `0x140046d00`
- `0x140064038`
- `0x1400641a4`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1400640b7`
- `KERNEL32!GetModuleFileNameW` at `0x1400640b7`
- `KERNEL32!GetFullPathNameW` at `0x1400640e6`
- `KERNEL32!GetFullPathNameW` at `0x1400640e6`

## pseudocode

```c
WCHAR *__fastcall GetDllPath(const unsigned __int16 *a1, unsigned __int64 a2)
{
  HMODULE v2; // rbx
  int v4; // edi
  signed int ModuleFileNameW; // eax
  WCHAR *v6; // rbx
  LPWSTR FilePart[2]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Filename[264]; // [rsp+30h] [rbp-228h] BYREF

  v2 = s_hInst;
  if ( !s_hInst )
    return 0;
  FilePart[0] = 0;
  if ( (int)StringCchLengthW(a1, a2, (unsigned __int64 *)FilePart) >= 0 && FilePart[0] )
    return &Buffer;
  v4 = 0;
  memset_0(Filename, 0, 0x20Au);
  ModuleFileNameW = GetModuleFileNameW(v2, Filename, 0x105u);
  v6 = &Buffer;
  if ( ModuleFileNameW && ModuleFileNameW <= 260 )
  {
    FilePart[0] = 0;
    if ( GetFullPathNameW(Filename, 0x105u, &Buffer, FilePart) - 1 <= 0x103
      && FilePart[0]
      && FilePart[0] >= (LPWSTR)word_1400C1222
      && *(FilePart[0] - 1) == 92 )
    {
      *FilePart[0] = 0;
      v4 = 1;
    }
    else
    {
      Buffer = 0;
    }
  }
  if ( v4 != 1 )
    return 0;
  return v6;
}

```

## disassembly

```asm
0x140064038  mov     [rsp+arg_0], rbx
0x14006403d  push    rdi
0x14006403e  sub     rsp, 250h
0x140064045  mov     rax, cs:__security_cookie
0x14006404c  xor     rax, rsp
0x14006404f  mov     [rsp+258h+var_18], rax
0x140064057  mov     rbx, cs:s_hInst
0x14006405e  test    rbx, rbx
0x140064061  jnz     short loc_14006406A
0x140064063  xor     eax, eax
0x140064065  jmp     loc_140064131
0x14006406a  lea     r8, [rsp+258h+FilePart]; unsigned __int64 *
0x14006406f  mov     [rsp+258h+FilePart], 0
0x140064078  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14006407d  test    eax, eax
0x14006407f  js      short loc_140064095
0x140064081  cmp     [rsp+258h+FilePart], 0
0x140064087  jbe     short loc_140064095
0x140064089  lea     rax, Buffer
0x140064090  jmp     loc_140064131
0x140064095  xor     edx, edx; Val
0x140064097  lea     rcx, [rsp+258h+Filename]; void *
0x14006409c  mov     r8d, 20Ah; Size
0x1400640a2  xor     edi, edi
0x1400640a4  call    memset_0
0x1400640a9  mov     r8d, 105h; nSize
0x1400640af  lea     rdx, [rsp+258h+Filename]; lpFilename
0x1400640b4  mov     rcx, rbx; hModule
0x1400640b7  call    cs:__imp_GetModuleFileNameW
0x1400640bd  lea     rbx, Buffer
0x1400640c4  test    eax, eax
0x1400640c6  jz      short loc_140064125
0x1400640c8  cmp     eax, 104h
0x1400640cd  jg      short loc_140064125
0x1400640cf  lea     r9, [rsp+258h+FilePart]; lpFilePart
0x1400640d4  mov     [rsp+258h+FilePart], rdi
0x1400640d9  mov     r8, rbx; lpBuffer
0x1400640dc  lea     rcx, [rsp+258h+Filename]; lpFileName
0x1400640e1  mov     edx, 105h; nBufferLength
0x1400640e6  call    cs:__imp_GetFullPathNameW
0x1400640ec  dec     eax
0x1400640ee  cmp     eax, 103h
0x1400640f3  ja      short loc_14006411C
0x1400640f5  mov     rcx, [rsp+258h+FilePart]
0x1400640fa  test    rcx, rcx
0x1400640fd  jz      short loc_14006411C
0x1400640ff  lea     rax, word_1400C1222
0x140064106  cmp     rcx, rax
0x140064109  jb      short loc_14006411C
0x14006410b  cmp     word ptr [rcx-2], 5Ch ; '\'
0x140064110  jnz     short loc_14006411C
0x140064112  xor     eax, eax
0x140064114  mov     [rcx], ax
0x140064117  lea     edi, [rax+1]
0x14006411a  jmp     short loc_140064125
0x14006411c  xor     ecx, ecx
0x14006411e  mov     cs:Buffer, cx
0x140064125  xor     ecx, ecx
0x140064127  cmp     edi, 1
0x14006412a  cmovnz  rbx, rcx
0x14006412e  mov     rax, rbx
0x140064131  mov     rcx, [rsp+258h+var_18]
0x140064139  xor     rcx, rsp; StackCookie
0x14006413c  call    __security_check_cookie
0x140064141  mov     rbx, [rsp+258h+arg_0]
0x140064149  add     rsp, 250h
0x140064150  pop     rdi
0x140064151  retn
```
