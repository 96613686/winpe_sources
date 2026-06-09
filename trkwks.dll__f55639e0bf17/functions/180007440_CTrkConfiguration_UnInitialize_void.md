# CTrkConfiguration::UnInitialize(void)

- ea: `0x180007440`
- end: `0x180007473`
- name: `?UnInitialize@CTrkConfiguration@@QEAAXXZ`
- size: `51`
- prototype: `void __fastcall(CTrkConfiguration *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003b8c`
- `0x18000556c`
- `0x180007408`
- `0x18000d9e4`
- `0x18000ef08`
- `0x18000ef2c`
- `0x18000ef50`
- `0x18000f704`
- `0x18000f83c`

## callees

- `0x180007440`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000745d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000745d`

## pseudocode

```c
void __fastcall CTrkConfiguration::UnInitialize(CTrkConfiguration *this)
{
  HKEY v2; // rcx

  if ( *(_DWORD *)this )
  {
    v2 = (HKEY)*((_QWORD *)this + 1);
    if ( v2 )
    {
      RegCloseKey(v2);
      *((_QWORD *)this + 1) = 0;
    }
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180007440  push    rbx
0x180007442  sub     rsp, 20h
0x180007446  cmp     dword ptr [rcx], 0
0x180007449  mov     rbx, rcx
0x18000744c  jnz     short loc_180007454
0x18000744e  add     rsp, 20h
0x180007452  pop     rbx
0x180007453  retn
0x180007454  mov     rcx, [rcx+8]; hKey
0x180007458  test    rcx, rcx
0x18000745b  jz      short loc_18000746B
0x18000745d  call    cs:__imp_RegCloseKey
0x180007463  mov     qword ptr [rbx+8], 0
0x18000746b  mov     dword ptr [rbx], 0
0x180007471  jmp     short loc_18000744E
```
