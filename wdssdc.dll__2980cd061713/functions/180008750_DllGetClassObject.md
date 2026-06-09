# DllGetClassObject

- ea: `0x180008750`
- end: `0x180008881`
- name: `DllGetClassObject`
- size: `305`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008750`
- `0x18000d010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000882c`
- `KERNEL32!LeaveCriticalSection` at `0x18000882c`
- `KERNEL32!EnterCriticalSection` at `0x1800087fb`
- `KERNEL32!EnterCriticalSection` at `0x1800087fb`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v7; // rcx
  __int64 *v8; // r9
  struct ATL::_ATL_OBJMAP_ENTRY30 *v9; // r14
  _DWORD *v10; // rdx
  _QWORD *v11; // rdi

  if ( !ATL::_AtlComModule )
    return -2147418113;
  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v6 = 0;
  v7 = off_180012140;
  v8 = off_180012148;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_180012148 )
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
0x180008750  mov     rax, rsp
0x180008753  mov     [rax+8], rbx
0x180008757  mov     [rax+10h], rbp
0x18000875b  mov     [rax+18h], rsi
0x18000875f  mov     [rax+20h], rdi
0x180008763  push    r14
0x180008765  sub     rsp, 20h
0x180008769  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180008770  mov     rsi, r8
0x180008773  mov     r8, rcx
0x180008776  mov     rbp, rdx
0x180008779  jnz     short loc_180008785
0x18000877b  mov     ebx, 8000FFFFh
0x180008780  jmp     loc_180008863
0x180008785  test    rsi, rsi
0x180008788  jnz     short loc_180008794
0x18000878a  mov     ebx, 80004003h
0x18000878f  jmp     loc_180008863
0x180008794  mov     qword ptr [rsi], 0
0x18000879b  xor     ebx, ebx
0x18000879d  mov     rcx, cs:off_180012140
0x1800087a4  mov     r9, cs:off_180012148
0x1800087ab  jmp     short loc_1800087E4
0x1800087ad  mov     r14, [rcx]
0x1800087b0  test    r14, r14
0x1800087b3  jz      short loc_1800087E0
0x1800087b5  cmp     [r14+10h], rbx
0x1800087b9  jz      short loc_1800087E0
0x1800087bb  mov     rdx, [r14]
0x1800087be  mov     eax, [rdx]
0x1800087c0  cmp     [r8], eax
0x1800087c3  jnz     short loc_1800087E0
0x1800087c5  mov     eax, [rdx+4]
0x1800087c8  cmp     [r8+4], eax
0x1800087cc  jnz     short loc_1800087E0
0x1800087ce  mov     eax, [rdx+8]
0x1800087d1  cmp     [r8+8], eax
0x1800087d5  jnz     short loc_1800087E0
0x1800087d7  mov     eax, [rdx+0Ch]
0x1800087da  cmp     [r8+0Ch], eax
0x1800087de  jz      short loc_1800087EB
0x1800087e0  add     rcx, 8
0x1800087e4  cmp     rcx, r9
0x1800087e7  jb      short loc_1800087AD
0x1800087e9  jmp     short loc_180008853
0x1800087eb  lea     rdi, [r14+20h]
0x1800087ef  cmp     [rdi], rbx
0x1800087f2  jnz     short loc_180008838
0x1800087f4  lea     rcx, CriticalSection; lpCriticalSection
0x1800087fb  call    cs:__imp_EnterCriticalSection
0x180008802  nop     dword ptr [rax+rax+00h]
0x180008807  cmp     [rdi], rbx
0x18000880a  jnz     short loc_180008825
0x18000880c  mov     rcx, [r14+18h]
0x180008810  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180008817  mov     rax, [r14+10h]
0x18000881b  mov     r8, rdi
0x18000881e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008823  mov     ebx, eax
0x180008825  lea     rcx, CriticalSection; lpCriticalSection
0x18000882c  call    cs:__imp_LeaveCriticalSection
0x180008833  nop     dword ptr [rax+rax+00h]
0x180008838  mov     rcx, [rdi]
0x18000883b  test    rcx, rcx
0x18000883e  jz      short loc_180008853
0x180008840  mov     rax, [rcx]
0x180008843  mov     r8, rsi
0x180008846  mov     rdx, rbp
0x180008849  mov     rax, [rax]
0x18000884c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008851  mov     ebx, eax
0x180008853  cmp     qword ptr [rsi], 0
0x180008857  jnz     short loc_180008863
0x180008859  test    ebx, ebx
0x18000885b  mov     eax, 80040111h
0x180008860  cmovz   ebx, eax
0x180008863  mov     rbp, [rsp+28h+arg_8]
0x180008868  mov     eax, ebx
0x18000886a  mov     rbx, [rsp+28h+arg_0]
0x18000886f  mov     rsi, [rsp+28h+arg_10]
0x180008874  mov     rdi, [rsp+28h+arg_18]
0x180008879  add     rsp, 20h
0x18000887d  pop     r14
0x18000887f  retn
```
