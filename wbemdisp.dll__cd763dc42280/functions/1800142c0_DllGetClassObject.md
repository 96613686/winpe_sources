# DllGetClassObject

- ea: `0x1800142c0`
- end: `0x180014509`
- name: `DllGetClassObject`
- size: `585`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800142c0`
- `0x180014510`
- `0x180014538`
- `0x180036010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001437a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800143cf`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800143f5`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014448`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014496`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800144b4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800144d2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800144f0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001437a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800143cf`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800143f5`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014448`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014496`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800144b4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800144d2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800144f0`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  CSWbemFactory *v10; // rax
  int v11; // edx
  CSWbemFactory *v12; // rbx
  unsigned int v13; // edx
  HRESULT v14; // edi
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax

  v5 = *(_QWORD *)&CLSID_SWbemLocator.Data1 - *(_QWORD *)&rclsid->Data1;
  if ( *(_QWORD *)&CLSID_SWbemLocator.Data1 == *(_QWORD *)&rclsid->Data1 )
    v5 = *(_QWORD *)CLSID_SWbemLocator.Data4 - *(_QWORD *)rclsid->Data4;
  if ( v5 )
  {
    v6 = *(_QWORD *)&CLSID_SWbemSink.Data1 - *(_QWORD *)&rclsid->Data1;
    if ( *(_QWORD *)&CLSID_SWbemSink.Data1 == *(_QWORD *)&rclsid->Data1 )
      v6 = *(_QWORD *)CLSID_SWbemSink.Data4 - *(_QWORD *)rclsid->Data4;
    if ( v6 )
    {
      v7 = *(_QWORD *)&CLSID_SWbemNamedValueSet.Data1 - *(_QWORD *)&rclsid->Data1;
      if ( *(_QWORD *)&CLSID_SWbemNamedValueSet.Data1 == *(_QWORD *)&rclsid->Data1 )
        v7 = *(_QWORD *)CLSID_SWbemNamedValueSet.Data4 - *(_QWORD *)rclsid->Data4;
      if ( v7 )
      {
        v8 = *(_QWORD *)&CLSID_SWbemObjectPath.Data1 - *(_QWORD *)&rclsid->Data1;
        if ( *(_QWORD *)&CLSID_SWbemObjectPath.Data1 == *(_QWORD *)&rclsid->Data1 )
          v8 = *(_QWORD *)CLSID_SWbemObjectPath.Data4 - *(_QWORD *)rclsid->Data4;
        if ( v8 )
        {
          v9 = *(_QWORD *)&CLSID_SWbemParseDN.Data1 - *(_QWORD *)&rclsid->Data1;
          if ( *(_QWORD *)&CLSID_SWbemParseDN.Data1 == *(_QWORD *)&rclsid->Data1 )
            v9 = *(_QWORD *)CLSID_SWbemParseDN.Data4 - *(_QWORD *)rclsid->Data4;
          if ( v9 )
          {
            v16 = *(_QWORD *)&CLSID_SWbemLastError.Data1 - *(_QWORD *)&rclsid->Data1;
            if ( *(_QWORD *)&CLSID_SWbemLastError.Data1 == *(_QWORD *)&rclsid->Data1 )
              v16 = *(_QWORD *)CLSID_SWbemLastError.Data4 - *(_QWORD *)rclsid->Data4;
            if ( v16 )
            {
              v17 = *(_QWORD *)&CLSID_SWbemDateTime.Data1 - *(_QWORD *)&rclsid->Data1;
              if ( *(_QWORD *)&CLSID_SWbemDateTime.Data1 == *(_QWORD *)&rclsid->Data1 )
                v17 = *(_QWORD *)CLSID_SWbemDateTime.Data4 - *(_QWORD *)rclsid->Data4;
              if ( v17 )
              {
                v18 = *(_QWORD *)&CLSID_SWbemRefresher.Data1 - *(_QWORD *)&rclsid->Data1;
                if ( *(_QWORD *)&CLSID_SWbemRefresher.Data1 == *(_QWORD *)&rclsid->Data1 )
                  v18 = *(_QWORD *)CLSID_SWbemRefresher.Data4 - *(_QWORD *)rclsid->Data4;
                if ( v18 )
                  goto LABEL_25;
                v10 = (CSWbemFactory *)CWin32DefaultArena::WbemMemAlloc(0x10u);
                if ( v10 )
                {
                  v11 = 7;
                  goto LABEL_18;
                }
              }
              else
              {
                v10 = (CSWbemFactory *)CWin32DefaultArena::WbemMemAlloc(0x10u);
                if ( v10 )
                {
                  v11 = 6;
                  goto LABEL_18;
                }
              }
            }
            else
            {
              v10 = (CSWbemFactory *)CWin32DefaultArena::WbemMemAlloc(0x10u);
              if ( v10 )
              {
                v11 = 4;
                goto LABEL_18;
              }
            }
          }
          else
          {
            v10 = (CSWbemFactory *)CWin32DefaultArena::WbemMemAlloc(0x10u);
            if ( v10 )
            {
              v11 = 3;
LABEL_18:
              v12 = CSWbemFactory::CSWbemFactory(v10, v11);
              goto LABEL_19;
            }
          }
        }
        else
        {
          v10 = (CSWbemFactory *)CWin32DefaultArena::WbemMemAlloc(0x10u);
          if ( v10 )
          {
            v11 = 2;
            goto LABEL_18;
          }
        }
      }
      else
      {
        v10 = (CSWbemFactory *)CWin32DefaultArena::WbemMemAlloc(0x10u);
        if ( v10 )
        {
          v11 = 1;
          goto LABEL_18;
        }
      }
    }
    else
    {
      v10 = (CSWbemFactory *)CWin32DefaultArena::WbemMemAlloc(0x10u);
      if ( v10 )
      {
        v11 = 5;
        goto LABEL_18;
      }
    }
  }
  else
  {
    v10 = (CSWbemFactory *)CWin32DefaultArena::WbemMemAlloc(0x10u);
    if ( v10 )
    {
      v11 = 0;
      goto LABEL_18;
    }
  }
  v12 = 0;
LABEL_19:
  if ( !v12 )
  {
LABEL_25:
    *ppv = 0;
    return -2147467259;
  }
  v14 = (**(__int64 (__fastcall ***)(CSWbemFactory *, const IID *const, LPVOID *))v12)(v12, riid, ppv);
  if ( v14 < 0 )
    CSWbemFactory::`scalar deleting destructor'(v12, v13);
  return v14;
}

```

## disassembly

```asm
0x1800142c0  mov     [rsp+arg_8], rsi
0x1800142c5  push    rdi
0x1800142c6  sub     rsp, 20h
0x1800142ca  mov     rax, qword ptr cs:CLSID_SWbemLocator.Data1
0x1800142d1  mov     rdi, r8
0x1800142d4  mov     rsi, rdx
0x1800142d7  sub     rax, [rcx]
0x1800142da  jnz     short loc_1800142E7
0x1800142dc  mov     rax, qword ptr cs:CLSID_SWbemLocator.Data4
0x1800142e3  sub     rax, [rcx+8]
0x1800142e7  mov     [rsp+28h+arg_0], rbx
0x1800142ec  test    rax, rax
0x1800142ef  jz      loc_1800143CA
0x1800142f5  mov     rax, qword ptr cs:CLSID_SWbemSink.Data1
0x1800142fc  sub     rax, [rcx]
0x1800142ff  jnz     short loc_18001430C
0x180014301  mov     rax, qword ptr cs:CLSID_SWbemSink.Data4
0x180014308  sub     rax, [rcx+8]
0x18001430c  test    rax, rax
0x18001430f  jz      loc_1800143F0
0x180014315  mov     rax, qword ptr cs:CLSID_SWbemNamedValueSet.Data1
0x18001431c  sub     rax, [rcx]
0x18001431f  jnz     short loc_18001432C
0x180014321  mov     rax, qword ptr cs:CLSID_SWbemNamedValueSet.Data4
0x180014328  sub     rax, [rcx+8]
0x18001432c  test    rax, rax
0x18001432f  jz      loc_1800144AF
0x180014335  mov     rax, qword ptr cs:CLSID_SWbemObjectPath.Data1
0x18001433c  sub     rax, [rcx]
0x18001433f  jnz     short loc_18001434C
0x180014341  mov     rax, qword ptr cs:CLSID_SWbemObjectPath.Data4
0x180014348  sub     rax, [rcx+8]
0x18001434c  test    rax, rax
0x18001434f  jz      loc_1800144CD
0x180014355  mov     rax, qword ptr cs:CLSID_SWbemParseDN.Data1
0x18001435c  sub     rax, [rcx]
0x18001435f  jnz     short loc_18001436C
0x180014361  mov     rax, qword ptr cs:CLSID_SWbemParseDN.Data4
0x180014368  sub     rax, [rcx+8]
0x18001436c  test    rax, rax
0x18001436f  jnz     loc_180014407
0x180014375  mov     ecx, 10h
0x18001437a  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180014380  test    rax, rax
0x180014383  jz      short loc_1800143DE
0x180014385  mov     edx, 3; int
0x18001438a  mov     rcx, rax; this
0x18001438d  call    ??0CSWbemFactory@@QEAA@H@Z; CSWbemFactory::CSWbemFactory(int)
0x180014392  mov     rbx, rax
0x180014395  test    rbx, rbx
0x180014398  jz      short loc_1800143E2
0x18001439a  mov     rax, [rbx]
0x18001439d  mov     r8, rdi
0x1800143a0  mov     rdx, rsi
0x1800143a3  mov     rcx, rbx
0x1800143a6  mov     rax, [rax]
0x1800143a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143ae  mov     edi, eax
0x1800143b0  test    eax, eax
0x1800143b2  js      loc_18001445D
0x1800143b8  mov     eax, edi
0x1800143ba  mov     rbx, [rsp+28h+arg_0]
0x1800143bf  mov     rsi, [rsp+28h+arg_8]
0x1800143c4  add     rsp, 20h
0x1800143c8  pop     rdi
0x1800143c9  retn
0x1800143ca  mov     ecx, 10h
0x1800143cf  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800143d5  test    rax, rax
0x1800143d8  jnz     loc_18001446A
0x1800143de  xor     ebx, ebx
0x1800143e0  jmp     short loc_180014395
0x1800143e2  mov     qword ptr [rdi], 0
0x1800143e9  mov     eax, 80004005h
0x1800143ee  jmp     short loc_1800143BA
0x1800143f0  mov     ecx, 10h
0x1800143f5  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800143fb  test    rax, rax
0x1800143fe  jz      short loc_1800143DE
0x180014400  mov     edx, 5
0x180014405  jmp     short loc_18001438A
0x180014407  mov     rax, qword ptr cs:CLSID_SWbemLastError.Data1
0x18001440e  sub     rax, [rcx]
0x180014411  jnz     short loc_18001441E
0x180014413  mov     rax, qword ptr cs:CLSID_SWbemLastError.Data4
0x18001441a  sub     rax, [rcx+8]
0x18001441e  test    rax, rax
0x180014421  jz      loc_1800144EB
0x180014427  mov     rax, qword ptr cs:CLSID_SWbemDateTime.Data1
0x18001442e  sub     rax, [rcx]
0x180014431  jnz     short loc_18001443E
0x180014433  mov     rax, qword ptr cs:CLSID_SWbemDateTime.Data4
0x18001443a  sub     rax, [rcx+8]
0x18001443e  test    rax, rax
0x180014441  jnz     short loc_180014471
0x180014443  mov     ecx, 10h
0x180014448  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001444e  test    rax, rax
0x180014451  jz      short loc_1800143DE
0x180014453  mov     edx, 6
0x180014458  jmp     loc_18001438A
0x18001445d  mov     rcx, rbx; this
0x180014460  call    ??_GCSWbemFactory@@QEAAPEAXI@Z; CSWbemFactory::`scalar deleting destructor'(uint)
0x180014465  jmp     loc_1800143B8
0x18001446a  xor     edx, edx
0x18001446c  jmp     loc_18001438A
0x180014471  mov     rax, qword ptr cs:CLSID_SWbemRefresher.Data1
0x180014478  sub     rax, [rcx]
0x18001447b  jnz     short loc_180014488
0x18001447d  mov     rax, qword ptr cs:CLSID_SWbemRefresher.Data4
0x180014484  sub     rax, [rcx+8]
0x180014488  test    rax, rax
0x18001448b  jnz     loc_1800143E2
0x180014491  mov     ecx, 10h
0x180014496  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001449c  test    rax, rax
0x18001449f  jz      loc_1800143DE
0x1800144a5  mov     edx, 7
0x1800144aa  jmp     loc_18001438A
0x1800144af  mov     ecx, 10h
0x1800144b4  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800144ba  test    rax, rax
0x1800144bd  jz      loc_1800143DE
0x1800144c3  mov     edx, 1
0x1800144c8  jmp     loc_18001438A
0x1800144cd  mov     ecx, 10h
0x1800144d2  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800144d8  test    rax, rax
0x1800144db  jz      loc_1800143DE
0x1800144e1  mov     edx, 2
0x1800144e6  jmp     loc_18001438A
0x1800144eb  mov     ecx, 10h
0x1800144f0  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800144f6  test    rax, rax
0x1800144f9  jz      loc_1800143DE
0x1800144ff  mov     edx, 4
0x180014504  jmp     loc_18001438A
```
