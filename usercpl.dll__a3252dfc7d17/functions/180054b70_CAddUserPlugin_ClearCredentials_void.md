# CAddUserPlugin::ClearCredentials(void)

- ea: `0x180054b70`
- end: `0x180054c4d`
- name: `?ClearCredentials@CAddUserPlugin@@UEAAXXZ`
- size: `221`
- prototype: `void __fastcall(CAddUserPlugin *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180054804`
- `0x180054c60`
- `0x180054c70`
- `0x180054c80`

## callees

- `0x180054b70`
- `0x18006e7f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054b88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054bb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054bd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054bea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054c19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054c31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054b88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054bb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054bd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054bea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054c19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054c31`

## pseudocode

```c
void __fastcall CAddUserPlugin::ClearCredentials(CAddUserPlugin *this)
{
  _BYTE *v2; // rcx
  __int64 v3; // rdx
  _BYTE *v4; // rax
  void *v5; // rcx
  void *v6; // rcx
  unsigned __int16 *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx

  *((_DWORD *)this + 25) = 0;
  CoTaskMemFree(*((LPVOID *)this + 13));
  v2 = (_BYTE *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 13) = 0;
  if ( v2 )
  {
    v3 = *((unsigned int *)this + 30);
    v4 = v2;
    if ( *((_DWORD *)this + 30) )
    {
      do
      {
        *v4++ = 0;
        --v3;
      }
      while ( v3 );
    }
    CoTaskMemFree(v2);
  }
  v5 = (void *)*((_QWORD *)this + 16);
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = 0;
  CoTaskMemFree(v5);
  v6 = (void *)*((_QWORD *)this + 23);
  *((_QWORD *)this + 16) = 0;
  CoTaskMemFree(v6);
  v7 = (unsigned __int16 *)*((_QWORD *)this + 24);
  *((_QWORD *)this + 23) = 0;
  ClearAndFreeSecretString(v7);
  v8 = (void *)*((_QWORD *)this + 25);
  *((_QWORD *)this + 24) = 0;
  CoTaskMemFree(v8);
  v9 = (void *)*((_QWORD *)this + 26);
  *((_QWORD *)this + 25) = 0;
  CoTaskMemFree(v9);
  *((_QWORD *)this + 26) = 0;
}

```

## disassembly

```asm
0x180054b70  mov     [rsp+arg_0], rbx
0x180054b75  push    rdi
0x180054b76  sub     rsp, 20h
0x180054b7a  mov     rbx, rcx
0x180054b7d  mov     dword ptr [rcx+64h], 0
0x180054b84  mov     rcx, [rcx+68h]; pv
0x180054b88  call    cs:__imp_CoTaskMemFree
0x180054b8e  mov     rcx, [rbx+70h]; pv
0x180054b92  mov     qword ptr [rbx+68h], 0
0x180054b9a  test    rcx, rcx
0x180054b9d  jz      short loc_180054BBC
0x180054b9f  mov     edx, [rbx+78h]
0x180054ba2  mov     rax, rcx
0x180054ba5  test    rdx, rdx
0x180054ba8  jz      short loc_180054BB6
0x180054baa  mov     byte ptr [rax], 0
0x180054bad  inc     rax
0x180054bb0  sub     rdx, 1
0x180054bb4  jnz     short loc_180054BAA
0x180054bb6  call    cs:__imp_CoTaskMemFree
0x180054bbc  mov     rcx, [rbx+80h]; pv
0x180054bc3  mov     qword ptr [rbx+70h], 0
0x180054bcb  mov     dword ptr [rbx+78h], 0
0x180054bd2  call    cs:__imp_CoTaskMemFree
0x180054bd8  mov     rcx, [rbx+0B8h]; pv
0x180054bdf  mov     qword ptr [rbx+80h], 0
0x180054bea  call    cs:__imp_CoTaskMemFree
0x180054bf0  mov     rcx, [rbx+0C0h]; unsigned __int16 *
0x180054bf7  mov     qword ptr [rbx+0B8h], 0
0x180054c02  call    ?ClearAndFreeSecretString@@YAXPEAG@Z; ClearAndFreeSecretString(ushort *)
0x180054c07  mov     rcx, [rbx+0C8h]; pv
0x180054c0e  mov     qword ptr [rbx+0C0h], 0
0x180054c19  call    cs:__imp_CoTaskMemFree
0x180054c1f  mov     rcx, [rbx+0D0h]; pv
0x180054c26  mov     qword ptr [rbx+0C8h], 0
0x180054c31  call    cs:__imp_CoTaskMemFree
0x180054c37  mov     qword ptr [rbx+0D0h], 0
0x180054c42  mov     rbx, [rsp+28h+arg_0]
0x180054c47  add     rsp, 20h
0x180054c4b  pop     rdi
0x180054c4c  retn
```
