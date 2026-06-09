# DllGetClassObject

- ea: `0x180011630`
- end: `0x180011743`
- name: `DllGetClassObject`
- size: `275`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180011630`
- `0x180014010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800116fe`
- `KERNEL32!LeaveCriticalSection` at `0x1800116fe`
- `KERNEL32!EnterCriticalSection` at `0x1800116cd`
- `KERNEL32!EnterCriticalSection` at `0x1800116cd`

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

  if ( !ATL::_AtlComModule )
    return -2147418113;
  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v6 = 0;
  v7 = off_18001B540;
  v8 = off_18001B548;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_18001B548 )
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
            EnterCriticalSection(&CriticalSection);
            if ( !*v11 )
              v6 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v9 + 2))(
                     *((_QWORD *)v9 + 3),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     (__int64)v9 + 32);
            LeaveCriticalSection(&CriticalSection);
          }
          if ( *v11 )
            v6 = (**(__int64 (__fastcall ***)(_QWORD, const IID *const, LPVOID *, __int64 *))*v11)(*v11, riid, ppv, v8);
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
0x180011630  push    rbx
0x180011632  push    rbp
0x180011633  push    rsi
0x180011634  push    rdi
0x180011635  push    r14
0x180011637  sub     rsp, 20h
0x18001163b  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180011642  mov     r14, r8
0x180011645  mov     r8, rcx
0x180011648  mov     rbp, rdx
0x18001164b  jnz     short loc_180011657
0x18001164d  mov     ebx, 8000FFFFh
0x180011652  jmp     loc_180011735
0x180011657  test    r14, r14
0x18001165a  jnz     short loc_180011666
0x18001165c  mov     ebx, 80004003h
0x180011661  jmp     loc_180011735
0x180011666  mov     qword ptr [r14], 0
0x18001166d  xor     ebx, ebx
0x18001166f  mov     rcx, cs:off_18001B540
0x180011676  mov     r9, cs:off_18001B548
0x18001167d  jmp     short loc_1800116B6
0x18001167f  mov     rsi, [rcx]
0x180011682  test    rsi, rsi
0x180011685  jz      short loc_1800116B2
0x180011687  cmp     [rsi+10h], rbx
0x18001168b  jz      short loc_1800116B2
0x18001168d  mov     rdx, [rsi]
0x180011690  mov     eax, [rdx]
0x180011692  cmp     [r8], eax
0x180011695  jnz     short loc_1800116B2
0x180011697  mov     eax, [rdx+4]
0x18001169a  cmp     [r8+4], eax
0x18001169e  jnz     short loc_1800116B2
0x1800116a0  mov     eax, [rdx+8]
0x1800116a3  cmp     [r8+8], eax
0x1800116a7  jnz     short loc_1800116B2
0x1800116a9  mov     eax, [rdx+0Ch]
0x1800116ac  cmp     [r8+0Ch], eax
0x1800116b0  jz      short loc_1800116BD
0x1800116b2  add     rcx, 8
0x1800116b6  cmp     rcx, r9
0x1800116b9  jb      short loc_18001167F
0x1800116bb  jmp     short loc_180011725
0x1800116bd  lea     rdi, [rsi+20h]
0x1800116c1  cmp     [rdi], rbx
0x1800116c4  jnz     short loc_18001170A
0x1800116c6  lea     rcx, CriticalSection; lpCriticalSection
0x1800116cd  call    cs:__imp_EnterCriticalSection
0x1800116d4  nop     dword ptr [rax+rax+00h]
0x1800116d9  cmp     [rdi], rbx
0x1800116dc  jnz     short loc_1800116F7
0x1800116de  mov     rcx, [rsi+18h]
0x1800116e2  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800116e9  mov     rax, [rsi+10h]
0x1800116ed  mov     r8, rdi
0x1800116f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116f5  mov     ebx, eax
0x1800116f7  lea     rcx, CriticalSection; lpCriticalSection
0x1800116fe  call    cs:__imp_LeaveCriticalSection
0x180011705  nop     dword ptr [rax+rax+00h]
0x18001170a  mov     rcx, [rdi]
0x18001170d  test    rcx, rcx
0x180011710  jz      short loc_180011725
0x180011712  mov     rax, [rcx]
0x180011715  mov     r8, r14
0x180011718  mov     rdx, rbp
0x18001171b  mov     rax, [rax]
0x18001171e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011723  mov     ebx, eax
0x180011725  cmp     qword ptr [r14], 0
0x180011729  jnz     short loc_180011735
0x18001172b  test    ebx, ebx
0x18001172d  mov     eax, 80040111h
0x180011732  cmovz   ebx, eax
0x180011735  mov     eax, ebx
0x180011737  add     rsp, 20h
0x18001173b  pop     r14
0x18001173d  pop     rdi
0x18001173e  pop     rsi
0x18001173f  pop     rbp
0x180011740  pop     rbx
0x180011741  retn
```
