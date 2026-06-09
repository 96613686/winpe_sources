# GenerateUniqueID(_GUID *)

- ea: `0x1800240e4`
- end: `0x180024152`
- name: `?GenerateUniqueID@@YAXPEAU_GUID@@@Z`
- size: `110`
- prototype: `void __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800247dc`

## callees

- `0x1800240e4`
- `0x18002e5b0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800240fc`
- `RPCRT4!UuidCreate` at `0x1800240fc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180024106`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180024106`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002411b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002411b`

## pseudocode

```c
void __fastcall GenerateUniqueID(struct _GUID *a1)
{
  struct _SYSTEMTIME SystemTime; // [rsp+20h] [rbp-28h] BYREF

  if ( UuidCreate(a1) )
  {
    a1->Data1 = GetTickCount();
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    a1->Data2 = SystemTime.wMilliseconds;
    a1->Data3 = SystemTime.wSecond;
    *(_WORD *)&a1->Data4[4] = SystemTime.wMinute;
    *(_DWORD *)a1->Data4 = (_DWORD)a1;
  }
}

```

## disassembly

```asm
0x1800240e4  push    rbx
0x1800240e6  sub     rsp, 40h
0x1800240ea  mov     rax, cs:__security_cookie
0x1800240f1  xor     rax, rsp
0x1800240f4  mov     [rsp+48h+var_18], rax
0x1800240f9  mov     rbx, rcx
0x1800240fc  call    cs:__imp_UuidCreate
0x180024102  test    eax, eax
0x180024104  jz      short loc_18002413F
0x180024106  call    cs:__imp_GetTickCount
0x18002410c  xorps   xmm0, xmm0
0x18002410f  lea     rcx, [rsp+48h+SystemTime]; lpSystemTime
0x180024114  mov     [rbx], eax
0x180024116  movups  xmmword ptr [rsp+48h+SystemTime.wYear], xmm0
0x18002411b  call    cs:__imp_GetSystemTime
0x180024121  movzx   eax, [rsp+48h+SystemTime.wMilliseconds]
0x180024126  mov     [rbx+4], ax
0x18002412a  movzx   eax, [rsp+48h+SystemTime.wSecond]
0x18002412f  mov     [rbx+6], ax
0x180024133  movzx   eax, [rsp+48h+SystemTime.wMinute]
0x180024138  mov     [rbx+0Ch], ax
0x18002413c  mov     [rbx+8], ebx
0x18002413f  mov     rcx, [rsp+48h+var_18]
0x180024144  xor     rcx, rsp; StackCookie
0x180024147  call    __security_check_cookie
0x18002414c  add     rsp, 40h
0x180024150  pop     rbx
0x180024151  retn
```
