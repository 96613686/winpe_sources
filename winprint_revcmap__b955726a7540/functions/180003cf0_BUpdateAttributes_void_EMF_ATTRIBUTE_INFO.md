# BUpdateAttributes(void *,_EMF_ATTRIBUTE_INFO *)

- ea: `0x180003cf0`
- end: `0x180003d73`
- name: `?BUpdateAttributes@@YAHPEAXPEAU_EMF_ATTRIBUTE_INFO@@@Z`
- size: `131`
- prototype: `__int64 __fastcall(HDC hdc, struct _EMF_ATTRIBUTE_INFO *)`
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800017d0`
- `0x180003200`
- `0x180006e10`
- `0x180007210`

## import_xrefs

- `GDI32!GetDeviceCaps` at `0x180003d05`
- `GDI32!GetDeviceCaps` at `0x180003d16`
- `GDI32!GetDeviceCaps` at `0x180003d27`
- `GDI32!GetDeviceCaps` at `0x180003d38`
- `GDI32!GetDeviceCaps` at `0x180003d49`
- `GDI32!GetDeviceCaps` at `0x180003d5a`
- `GDI32!GetDeviceCaps` at `0x180003d05`
- `GDI32!GetDeviceCaps` at `0x180003d16`
- `GDI32!GetDeviceCaps` at `0x180003d27`
- `GDI32!GetDeviceCaps` at `0x180003d38`
- `GDI32!GetDeviceCaps` at `0x180003d49`
- `GDI32!GetDeviceCaps` at `0x180003d5a`

## pseudocode

```c
__int64 __fastcall BUpdateAttributes(HDC hdc, struct _EMF_ATTRIBUTE_INFO *a2)
{
  *((_DWORD *)a2 + 1) = GetDeviceCaps(hdc, 88);
  *((_DWORD *)a2 + 2) = GetDeviceCaps(hdc, 90);
  *((_DWORD *)a2 + 5) = GetDeviceCaps(hdc, 118);
  *((_DWORD *)a2 + 6) = GetDeviceCaps(hdc, 117);
  *((_DWORD *)a2 + 3) = GetDeviceCaps(hdc, 110);
  *((_DWORD *)a2 + 4) = GetDeviceCaps(hdc, 111);
  return 1;
}

```

## disassembly

```asm
0x180003cf0  mov     [rsp+arg_0], rbx
0x180003cf5  push    rdi
0x180003cf6  sub     rsp, 20h
0x180003cfa  mov     rdi, rdx
0x180003cfd  mov     rbx, rcx
0x180003d00  mov     edx, 58h ; 'X'; index
0x180003d05  call    cs:__imp_GetDeviceCaps
0x180003d0b  mov     edx, 5Ah ; 'Z'; index
0x180003d10  mov     rcx, rbx; hdc
0x180003d13  mov     [rdi+4], eax
0x180003d16  call    cs:__imp_GetDeviceCaps
0x180003d1c  mov     edx, 76h ; 'v'; index
0x180003d21  mov     rcx, rbx; hdc
0x180003d24  mov     [rdi+8], eax
0x180003d27  call    cs:__imp_GetDeviceCaps
0x180003d2d  mov     edx, 75h ; 'u'; index
0x180003d32  mov     rcx, rbx; hdc
0x180003d35  mov     [rdi+14h], eax
0x180003d38  call    cs:__imp_GetDeviceCaps
0x180003d3e  mov     edx, 6Eh ; 'n'; index
0x180003d43  mov     rcx, rbx; hdc
0x180003d46  mov     [rdi+18h], eax
0x180003d49  call    cs:__imp_GetDeviceCaps
0x180003d4f  mov     edx, 6Fh ; 'o'; index
0x180003d54  mov     rcx, rbx; hdc
0x180003d57  mov     [rdi+0Ch], eax
0x180003d5a  call    cs:__imp_GetDeviceCaps
0x180003d60  mov     rbx, [rsp+28h+arg_0]
0x180003d65  mov     [rdi+10h], eax
0x180003d68  mov     eax, 1
0x180003d6d  add     rsp, 20h
0x180003d71  pop     rdi
0x180003d72  retn
```
