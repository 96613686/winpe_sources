# CRegSetting::GetDwordData(void)

- ea: `0x180009b40`
- end: `0x180009b6e`
- name: `?GetDwordData@CRegSetting@@QEBAKXZ`
- size: `46`
- prototype: `int __fastcall(CRegSetting *this)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006550`
- `0x180009cf0`
- `0x18000a8f4`
- `0x18000f834`
- `0x18000ff3c`
- `0x180010234`
- `0x18001326c`

## callees

- `0x180009b40`

## import_xrefs

- `msvcrt!wcstol` at `0x180009b63`

## pseudocode

```c
int __fastcall CRegSetting::GetDwordData(CRegSetting *this)
{
  if ( !*(_BYTE *)this )
    return *((_DWORD *)this + 24);
  if ( !*((_DWORD *)this + 1) )
    return **((_DWORD **)this + 1);
  if ( *((_DWORD *)this + 1) == 1 )
    return wcstol(*((const wchar_t **)this + 1), 0, 10);
  else
    return *((_DWORD *)this + 24);
}

```

## disassembly

```asm
0x180009b40  cmp     byte ptr [rcx], 0
0x180009b43  jz      short loc_180009B6A
0x180009b45  cmp     dword ptr [rcx+4], 0
0x180009b49  jnz     short loc_180009B53
0x180009b4b  mov     rax, [rcx+8]
0x180009b4f  mov     eax, [rax]
0x180009b51  jmp     short locret_180009B6D
0x180009b53  cmp     dword ptr [rcx+4], 1
0x180009b57  jnz     short loc_180009B6A
0x180009b59  mov     rcx, [rcx+8]
0x180009b5d  xor     edx, edx
0x180009b5f  lea     r8d, [rdx+0Ah]
0x180009b63  jmp     cs:__imp_wcstol
0x180009b6a  mov     eax, [rcx+60h]
0x180009b6d  retn
```
