# SortChildrenProc(void const *,void const *)

- ea: `0x18000dcd0`
- end: `0x18000dd78`
- name: `?SortChildrenProc@@YAHPEBX0@Z`
- size: `168`
- prototype: `__int64 __fastcall(const void *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000dcd0`
- `0x18001e010`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x18000dd3a`
- `KERNEL32!lstrcmpW` at `0x18000dd3a`
- `ole32!CoTaskMemFree` at `0x18000dd47`
- `ole32!CoTaskMemFree` at `0x18000dd52`
- `ole32!CoTaskMemFree` at `0x18000dd47`
- `ole32!CoTaskMemFree` at `0x18000dd52`

## pseudocode

```c
__int64 __fastcall SortChildrenProc(__int64 **a1, _DWORD **a2)
{
  __int64 *v2; // rcx
  unsigned int v3; // ebx
  _DWORD *v4; // rdi
  __int64 v5; // rax
  LPCWSTR lpString1; // [rsp+30h] [rbp+8h] BYREF
  LPCWSTR lpString2; // [rsp+38h] [rbp+10h] BYREF

  v2 = *a1;
  v3 = 0;
  if ( v2 )
  {
    v4 = *a2;
    if ( *a2 )
    {
      if ( *((_DWORD *)v2 + 30) == -3 )
      {
        return v4[30] != -3;
      }
      else if ( v4[30] == -3 )
      {
        return (unsigned int)-1;
      }
      else
      {
        v5 = *v2;
        lpString1 = 0;
        lpString2 = 0;
        (*(void (__fastcall **)(__int64 *, LPCWSTR *))(v5 + 360))(v2, &lpString1);
        (*(void (__fastcall **)(_DWORD *, LPCWSTR *))(*(_QWORD *)v4 + 360LL))(v4, &lpString2);
        v3 = lstrcmpW(lpString1, lpString2);
        CoTaskMemFree((LPVOID)lpString1);
        CoTaskMemFree((LPVOID)lpString2);
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000dcd0  mov     r11, rsp
0x18000dcd3  mov     [r11+18h], rbx
0x18000dcd7  push    rdi
0x18000dcd8  sub     rsp, 20h
0x18000dcdc  mov     rcx, [rcx]
0x18000dcdf  xor     ebx, ebx
0x18000dce1  test    rcx, rcx
0x18000dce4  jz      loc_18000DD6B
0x18000dcea  mov     rdi, [rdx]
0x18000dced  test    rdi, rdi
0x18000dcf0  jz      short loc_18000DD6B
0x18000dcf2  cmp     dword ptr [rcx+78h], 0FFFFFFFDh
0x18000dcf6  jz      short loc_18000DD5F
0x18000dcf8  cmp     dword ptr [rdi+78h], 0FFFFFFFDh
0x18000dcfc  jz      short loc_18000DD5A
0x18000dcfe  mov     rax, [rcx]
0x18000dd01  lea     rdx, [r11+8]
0x18000dd05  mov     [r11+8], rbx
0x18000dd09  mov     [r11+10h], rbx
0x18000dd0d  mov     rax, [rax+168h]
0x18000dd14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd19  mov     rax, [rdi]
0x18000dd1c  lea     rdx, [rsp+28h+lpString2]
0x18000dd21  mov     rcx, rdi
0x18000dd24  mov     rax, [rax+168h]
0x18000dd2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd30  mov     rdx, [rsp+28h+lpString2]; lpString2
0x18000dd35  mov     rcx, [rsp+28h+lpString1]; lpString1
0x18000dd3a  call    cs:__imp_lstrcmpW
0x18000dd40  mov     rcx, [rsp+28h+lpString1]; pv
0x18000dd45  mov     ebx, eax
0x18000dd47  call    cs:__imp_CoTaskMemFree
0x18000dd4d  mov     rcx, [rsp+28h+lpString2]; pv
0x18000dd52  call    cs:__imp_CoTaskMemFree
0x18000dd58  jmp     short loc_18000DD6B
0x18000dd5a  or      ebx, 0FFFFFFFFh
0x18000dd5d  jmp     short loc_18000DD6B
0x18000dd5f  cmp     dword ptr [rdi+78h], 0FFFFFFFDh
0x18000dd63  mov     eax, 1
0x18000dd68  cmovnz  ebx, eax
0x18000dd6b  mov     eax, ebx
0x18000dd6d  mov     rbx, [rsp+28h+arg_10]
0x18000dd72  add     rsp, 20h
0x18000dd76  pop     rdi
0x18000dd77  retn
```
