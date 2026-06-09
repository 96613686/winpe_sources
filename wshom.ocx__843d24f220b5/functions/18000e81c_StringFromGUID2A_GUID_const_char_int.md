# StringFromGUID2A(_GUID const &,char *,int)

- ea: `0x18000e81c`
- end: `0x18000e8b0`
- name: `?StringFromGUID2A@@YAHAEBU_GUID@@PEADH@Z`
- size: `148`
- prototype: `int(const struct _GUID *, char *, int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e1b0`
- `0x18000e8b8`
- `0x18000ee4c`

## import_xrefs

- `msvcrt!sprintf_s` at `0x18000e898`
- `msvcrt!sprintf_s` at `0x18000e898`

## pseudocode

```c
__int64 __fastcall StringFromGUID2A(const struct _GUID *a1, char *a2)
{
  sprintf_s(
    a2,
    0x64u,
    "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
    a1->Data1,
    a1->Data2,
    a1->Data3,
    a1->Data4[0],
    a1->Data4[1],
    a1->Data4[2],
    a1->Data4[3],
    a1->Data4[4],
    a1->Data4[5],
    a1->Data4[6],
    a1->Data4[7]);
  return 39;
}

```

## disassembly

```asm
0x18000e81c  push    rbx
0x18000e81e  push    rbp
0x18000e81f  push    rsi
0x18000e820  push    rdi
0x18000e821  push    r14
0x18000e823  push    r15
0x18000e825  sub     rsp, 78h
0x18000e829  movzx   r8d, byte ptr [rcx+0Eh]
0x18000e82e  mov     r15, rdx
0x18000e831  movzx   r9d, byte ptr [rcx+0Dh]
0x18000e836  mov     edx, 64h ; 'd'; BufferCount
0x18000e83b  movzx   eax, byte ptr [rcx+0Fh]
0x18000e83f  movzx   r10d, byte ptr [rcx+0Ch]
0x18000e844  movzx   r11d, byte ptr [rcx+0Bh]
0x18000e849  movzx   ebx, byte ptr [rcx+0Ah]
0x18000e84d  movzx   edi, byte ptr [rcx+9]
0x18000e851  movzx   esi, byte ptr [rcx+8]
0x18000e855  movzx   ebp, word ptr [rcx+6]
0x18000e859  movzx   r14d, word ptr [rcx+4]
0x18000e85e  mov     [rsp+0A8h+var_40], eax
0x18000e862  mov     [rsp+0A8h+var_48], r8d
0x18000e867  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x18000e86e  mov     [rsp+0A8h+var_50], r9d
0x18000e873  mov     r9d, [rcx]
0x18000e876  mov     rcx, r15; Buffer
0x18000e879  mov     [rsp+0A8h+var_58], r10d
0x18000e87e  mov     [rsp+0A8h+var_60], r11d
0x18000e883  mov     [rsp+0A8h+var_68], ebx
0x18000e887  mov     [rsp+0A8h+var_70], edi
0x18000e88b  mov     [rsp+0A8h+var_78], esi
0x18000e88f  mov     [rsp+0A8h+var_80], ebp
0x18000e893  mov     [rsp+0A8h+var_88], r14d
0x18000e898  call    cs:__imp_sprintf_s
0x18000e89e  mov     eax, 27h ; '''
0x18000e8a3  add     rsp, 78h
0x18000e8a7  pop     r15
0x18000e8a9  pop     r14
0x18000e8ab  pop     rdi
0x18000e8ac  pop     rsi
0x18000e8ad  pop     rbp
0x18000e8ae  pop     rbx
0x18000e8af  retn
```
