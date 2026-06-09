# GenerateUniqueID(_GUID *)

- ea: `0x180025794`
- end: `0x180025815`
- name: `?GenerateUniqueID@@YAXPEAU_GUID@@@Z`
- size: `129`
- prototype: `void __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025ed4`

## callees

- `0x180025794`
- `0x180030700`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800257ac`
- `RPCRT4!UuidCreate` at `0x1800257ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800257bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800257bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800257d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800257d7`

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
0x180025794  push    rbx
0x180025796  sub     rsp, 40h
0x18002579a  mov     rax, cs:__security_cookie
0x1800257a1  xor     rax, rsp
0x1800257a4  mov     [rsp+48h+var_18], rax
0x1800257a9  mov     rbx, rcx
0x1800257ac  call    cs:__imp_UuidCreate
0x1800257b3  nop     dword ptr [rax+rax+00h]
0x1800257b8  test    eax, eax
0x1800257ba  jz      short loc_180025801
0x1800257bc  call    cs:__imp_GetTickCount
0x1800257c3  nop     dword ptr [rax+rax+00h]
0x1800257c8  xorps   xmm0, xmm0
0x1800257cb  lea     rcx, [rsp+48h+SystemTime]; lpSystemTime
0x1800257d0  mov     [rbx], eax
0x1800257d2  movups  xmmword ptr [rsp+48h+SystemTime.wYear], xmm0
0x1800257d7  call    cs:__imp_GetSystemTime
0x1800257de  nop     dword ptr [rax+rax+00h]
0x1800257e3  movzx   eax, [rsp+48h+SystemTime.wMilliseconds]
0x1800257e8  mov     [rbx+4], ax
0x1800257ec  movzx   eax, [rsp+48h+SystemTime.wSecond]
0x1800257f1  mov     [rbx+6], ax
0x1800257f5  movzx   eax, [rsp+48h+SystemTime.wMinute]
0x1800257fa  mov     [rbx+0Ch], ax
0x1800257fe  mov     [rbx+8], ebx
0x180025801  mov     rcx, [rsp+48h+var_18]
0x180025806  xor     rcx, rsp; StackCookie
0x180025809  call    __security_check_cookie
0x18002580e  add     rsp, 40h
0x180025812  pop     rbx
0x180025813  retn
```
