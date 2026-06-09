# SecSnapDelayLoadDll(_DLL_SECURITY_PACKAGE *)

- ea: `0x18001c99c`
- end: `0x18001c9f9`
- name: `?SecSnapDelayLoadDll@@YAJPEAU_DLL_SECURITY_PACKAGE@@@Z`
- size: `93`
- prototype: `__int64 __fastcall(struct _DLL_SECURITY_PACKAGE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008fc4`

## callees

- `0x180016694`
- `0x18001c99c`

## pseudocode

```c
__int64 __fastcall SecSnapDelayLoadDll(struct _DLL_SECURITY_PACKAGE *a1)
{
  struct _SECP_DLL_BINDING *v2; // rcx
  __int64 result; // rax
  struct _SECURITY_FUNCTION_TABLE_W *v4; // rdx
  struct _SECURITY_FUNCTION_TABLE_A *v5; // rcx
  int v6; // [rsp+30h] [rbp+8h] BYREF
  struct _SECURITY_FUNCTION_TABLE_W *v7; // [rsp+38h] [rbp+10h] BYREF
  struct _SECURITY_FUNCTION_TABLE_A *v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  v2 = (struct _SECP_DLL_BINDING *)*((_QWORD *)a1 + 7);
  v7 = 0;
  result = SecpBindSspiDll(v2, &v8, &v7, &v6);
  if ( !(_DWORD)result )
  {
    v4 = v7;
    v5 = v8;
    *((_DWORD *)a1 + 9) &= ~4u;
    *((_QWORD *)a1 + 21) = v4;
    *((_QWORD *)a1 + 22) = v4;
    *((_QWORD *)a1 + 20) = v5;
  }
  return result;
}

```

## disassembly

```asm
0x18001c99c  mov     rax, rsp
0x18001c99f  push    rbx
0x18001c9a0  sub     rsp, 20h
0x18001c9a4  mov     rbx, rcx
0x18001c9a7  mov     qword ptr [rax+18h], 0
0x18001c9af  mov     rcx, [rcx+38h]; struct _SECP_DLL_BINDING *
0x18001c9b3  lea     r9, [rax+8]; int *
0x18001c9b7  lea     r8, [rax+10h]; struct _SECURITY_FUNCTION_TABLE_W **
0x18001c9bb  mov     qword ptr [rax+10h], 0
0x18001c9c3  lea     rdx, [rax+18h]; struct _SECURITY_FUNCTION_TABLE_A **
0x18001c9c7  call    ?SecpBindSspiDll@@YAJPEAU_SECP_DLL_BINDING@@PEAPEAU_SECURITY_FUNCTION_TABLE_A@@PEAPEAU_SECURITY_FUNCTION_TABLE_W@@PEAH@Z; SecpBindSspiDll(_SECP_DLL_BINDING *,_SECURITY_FUNCTION_TABLE_A * *,_SECURITY_FUNCTION_TABLE_W * *,int *)
0x18001c9cc  test    eax, eax
0x18001c9ce  jnz     short loc_18001C9F3
0x18001c9d0  mov     rdx, [rsp+28h+arg_8]
0x18001c9d5  mov     rcx, [rsp+28h+arg_10]
0x18001c9da  and     dword ptr [rbx+24h], 0FFFFFFFBh
0x18001c9de  mov     [rbx+0A8h], rdx
0x18001c9e5  mov     [rbx+0B0h], rdx
0x18001c9ec  mov     [rbx+0A0h], rcx
0x18001c9f3  add     rsp, 20h
0x18001c9f7  pop     rbx
0x18001c9f8  retn
```
