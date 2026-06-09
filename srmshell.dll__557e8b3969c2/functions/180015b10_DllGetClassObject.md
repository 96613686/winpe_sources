# DllGetClassObject

- ea: `0x180015b10`
- end: `0x180015c2e`
- name: `DllGetClassObject`
- size: `286`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180015b10`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015be9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015be9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015bbb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015bbb`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v7; // rcx
  __int64 *v8; // r9
  struct ATL::_ATL_OBJMAP_ENTRY30 *v9; // rsi
  _DWORD *v10; // rdx
  _QWORD *v11; // rdi
  _RTL_CRITICAL_SECTION *v13; // [rsp+20h] [rbp-48h]
  char v14; // [rsp+28h] [rbp-40h]

  if ( !ATL::_AtlComModule )
    return -2147418113;
  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v6 = 0;
  v7 = off_18002B290;
  v8 = off_18002B298;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_18002B298 )
  {
    v9 = *v7;
    if ( *v7 )
    {
      if ( *((_QWORD *)v9 + 2) )
      {
        v10 = *(_DWORD **)v9;
        if ( rclsid->Data1 == **(_DWORD **)v9
          && *(_DWORD *)&rclsid->Data2 == v10[1]
          && *(_DWORD *)rclsid->Data4 == v10[2]
          && *(_DWORD *)&rclsid->Data4[4] == v10[3] )
        {
          v11 = (_QWORD *)((char *)v9 + 32);
          if ( !*((_QWORD *)v9 + 4) )
          {
            v13 = &CriticalSection;
            EnterCriticalSection(&CriticalSection);
            v6 = 0;
            if ( !*v11 )
              v6 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v9 + 2))(
                     *((_QWORD *)v9 + 3),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     (__int64)v9 + 32);
            LeaveCriticalSection(&CriticalSection);
            v14 = 0;
          }
          if ( *v11 )
            v6 = (**(__int64 (__fastcall ***)(_QWORD, const IID *const, LPVOID *, __int64 *, _RTL_CRITICAL_SECTION *, char))*v11)(
                   *v11,
                   riid,
                   ppv,
                   v8,
                   v13,
                   v14);
          break;
        }
      }
    }
    ++v7;
  }
  if ( !*ppv && !v6 )
    return -2147221231;
  return v6;
}

```

## disassembly

```asm
0x180015b10  push    rbx
0x180015b12  push    rbp
0x180015b13  push    rsi
0x180015b14  push    rdi
0x180015b15  push    r12
0x180015b17  push    r14
0x180015b19  sub     rsp, 38h
0x180015b1d  mov     r14, r8
0x180015b20  mov     rbp, rdx
0x180015b23  mov     r8, rcx
0x180015b26  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180015b2d  jnz     short loc_180015B39
0x180015b2f  mov     ebx, 8000FFFFh
0x180015b34  jmp     loc_180015C1F
0x180015b39  test    r14, r14
0x180015b3c  jnz     short loc_180015B48
0x180015b3e  mov     ebx, 80004003h
0x180015b43  jmp     loc_180015C1F
0x180015b48  mov     qword ptr [r14], 0
0x180015b4f  xor     ebx, ebx
0x180015b51  mov     rcx, cs:off_18002B290
0x180015b58  mov     r9, cs:off_18002B298
0x180015b5f  jmp     short loc_180015B98
0x180015b61  mov     rsi, [rcx]
0x180015b64  test    rsi, rsi
0x180015b67  jz      short loc_180015B94
0x180015b69  cmp     [rsi+10h], rbx
0x180015b6d  jz      short loc_180015B94
0x180015b6f  mov     rdx, [rsi]
0x180015b72  mov     eax, [rdx]
0x180015b74  cmp     [r8], eax
0x180015b77  jnz     short loc_180015B94
0x180015b79  mov     eax, [rdx+4]
0x180015b7c  cmp     [r8+4], eax
0x180015b80  jnz     short loc_180015B94
0x180015b82  mov     eax, [rdx+8]
0x180015b85  cmp     [r8+8], eax
0x180015b89  jnz     short loc_180015B94
0x180015b8b  mov     eax, [rdx+0Ch]
0x180015b8e  cmp     [r8+0Ch], eax
0x180015b92  jz      short loc_180015B9F
0x180015b94  add     rcx, 8
0x180015b98  cmp     rcx, r9
0x180015b9b  jb      short loc_180015B61
0x180015b9d  jmp     short loc_180015C0F
0x180015b9f  lea     rdi, [rsi+20h]
0x180015ba3  cmp     [rdi], rbx
0x180015ba6  jnz     short loc_180015BF4
0x180015ba8  lea     r12, CriticalSection
0x180015baf  mov     [rsp+68h+var_48], r12
0x180015bb4  mov     [rsp+68h+var_40], bl
0x180015bb8  mov     rcx, r12; lpCriticalSection
0x180015bbb  call    cs:__imp_EnterCriticalSection
0x180015bc1  mov     [rsp+68h+var_40], 1
0x180015bc6  xor     ebx, ebx
0x180015bc8  cmp     [rdi], rbx
0x180015bcb  jnz     short loc_180015BE6
0x180015bcd  mov     r8, rdi
0x180015bd0  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180015bd7  mov     rcx, [rsi+18h]
0x180015bdb  mov     rax, [rsi+10h]
0x180015bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015be4  mov     ebx, eax
0x180015be6  mov     rcx, r12; lpCriticalSection
0x180015be9  call    cs:__imp_LeaveCriticalSection
0x180015bef  mov     [rsp+68h+var_40], 0
0x180015bf4  mov     rcx, [rdi]
0x180015bf7  test    rcx, rcx
0x180015bfa  jz      short loc_180015C0F
0x180015bfc  mov     rax, [rcx]
0x180015bff  mov     r8, r14
0x180015c02  mov     rdx, rbp
0x180015c05  mov     rax, [rax]
0x180015c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c0d  mov     ebx, eax
0x180015c0f  cmp     qword ptr [r14], 0
0x180015c13  jnz     short loc_180015C1F
0x180015c15  mov     eax, 80040111h
0x180015c1a  test    ebx, ebx
0x180015c1c  cmovz   ebx, eax
0x180015c1f  mov     eax, ebx
0x180015c21  add     rsp, 38h
0x180015c25  pop     r14
0x180015c27  pop     r12
0x180015c29  pop     rdi
0x180015c2a  pop     rsi
0x180015c2b  pop     rbp
0x180015c2c  pop     rbx
0x180015c2d  retn
```
