# DllGetClassObject

- ea: `0x180010680`
- end: `0x180010777`
- name: `DllGetClassObject`
- size: `247`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180010680`
- `0x180010780`
- `0x1800150c4`
- `0x180086010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v4; // rax
  int i; // edx
  const struct CWMDSPComClassTemplate *v6; // rdi
  __int64 v7; // rax
  CClassFactory *v8; // rax
  CClassFactory *v9; // rax
  __int64 v11; // rax

  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v4 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v4 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( !v4 )
    goto LABEL_5;
  v11 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IClassFactory.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IClassFactory.Data1 )
    v11 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IClassFactory.Data4;
  if ( v11 )
    return -2147467262;
LABEL_5:
  for ( i = 0; ; ++i )
  {
    if ( i >= 4 )
      return -2147221231;
    v6 = (const struct CWMDSPComClassTemplate *)(&g_ComClassTemplates + 5 * i);
    v7 = **(_QWORD **)v6 - *(_QWORD *)&rclsid->Data1;
    if ( !v7 )
      v7 = *(_QWORD *)(*(_QWORD *)v6 + 8LL) - *(_QWORD *)rclsid->Data4;
    if ( !v7 )
      break;
  }
  v8 = (CClassFactory *)operator new(0x18u);
  if ( v8 )
  {
    v9 = CClassFactory::CClassFactory(v8, v6);
    *ppv = v9;
    if ( v9 )
    {
      (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v9 + 8LL))(v9);
      return 0;
    }
  }
  else
  {
    *ppv = 0;
  }
  return -2147024882;
}

```

## disassembly

```asm
0x180010680  mov     [rsp+arg_0], rbx
0x180010685  push    rdi
0x180010686  sub     rsp, 20h
0x18001068a  mov     rbx, r8
0x18001068d  mov     r8, rcx
0x180010690  test    rbx, rbx
0x180010693  jz      loc_18001075B
0x180010699  mov     qword ptr [rbx], 0
0x1800106a0  mov     rax, [rdx]
0x1800106a3  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x1800106aa  jnz     short loc_1800106B7
0x1800106ac  mov     rax, [rdx+8]
0x1800106b0  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x1800106b7  test    rax, rax
0x1800106ba  jnz     short loc_180010734
0x1800106bc  xor     edx, edx
0x1800106be  cmp     edx, 4
0x1800106c1  jge     loc_180010770
0x1800106c7  movsxd  rax, edx
0x1800106ca  lea     rcx, [rax+rax*4]
0x1800106ce  lea     rax, ?g_ComClassTemplates@@3PAUCWMDSPComClassTemplate@@A; CWMDSPComClassTemplate near * g_ComClassTemplates
0x1800106d5  lea     rdi, [rax+rcx*8]
0x1800106d9  mov     rcx, [rdi]
0x1800106dc  mov     rax, [rcx]
0x1800106df  sub     rax, [r8]
0x1800106e2  jnz     short loc_1800106EC
0x1800106e4  mov     rax, [rcx+8]
0x1800106e8  sub     rax, [r8+8]
0x1800106ec  test    rax, rax
0x1800106ef  jnz     short loc_180010730
0x1800106f1  lea     ecx, [rax+18h]; Size
0x1800106f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800106f9  test    rax, rax
0x1800106fc  jz      short loc_180010762
0x1800106fe  mov     rdx, rdi; struct CWMDSPComClassTemplate *
0x180010701  mov     rcx, rax; this
0x180010704  call    ??0CClassFactory@@QEAA@PEBUCWMDSPComClassTemplate@@@Z; CClassFactory::CClassFactory(CWMDSPComClassTemplate const *)
0x180010709  mov     [rbx], rax
0x18001070c  mov     rdx, rax
0x18001070f  test    rax, rax
0x180010712  jz      short loc_180010769
0x180010714  mov     rcx, [rax]
0x180010717  mov     rax, [rcx+8]
0x18001071b  mov     rcx, rdx
0x18001071e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010723  xor     eax, eax
0x180010725  mov     rbx, [rsp+28h+arg_0]
0x18001072a  add     rsp, 20h
0x18001072e  pop     rdi
0x18001072f  retn
0x180010730  inc     edx
0x180010732  jmp     short loc_1800106BE
0x180010734  mov     rax, [rdx]
0x180010737  sub     rax, qword ptr cs:IID_IClassFactory.Data1
0x18001073e  jnz     short loc_18001074B
0x180010740  mov     rax, [rdx+8]
0x180010744  sub     rax, qword ptr cs:IID_IClassFactory.Data4
0x18001074b  test    rax, rax
0x18001074e  jz      loc_1800106BC
0x180010754  mov     eax, 80004002h
0x180010759  jmp     short loc_180010725
0x18001075b  mov     eax, 80004003h
0x180010760  jmp     short loc_180010725
0x180010762  mov     qword ptr [rbx], 0
0x180010769  mov     eax, 8007000Eh
0x18001076e  jmp     short loc_180010725
0x180010770  mov     eax, 80040111h
0x180010775  jmp     short loc_180010725
```
