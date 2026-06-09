# ATL::CreateNormalizedObject

- ea: `0x18001585c`
- end: `0x180015a89`
- name: `ATL::CreateNormalizedObject`
- size: `557`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, BSTR pbstr)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800150b0`

## callees

- `0x180002da0`
- `0x18000bea0`
- `0x180013638`
- `0x18001585c`
- `0x180063010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800159d6`
- `OLEAUT32!__imp_SysStringLen` at `0x1800159d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015932`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015a5a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015932`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015a5a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800159bb`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800159bb`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800159c3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800159c3`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180015a02`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180015a02`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001596b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015976`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015984`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001596b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015976`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015984`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CreateNormalizedObject(unsigned __int16 *a1, __int64 a2, LPVOID *a3, _BYTE *a4, BSTR pbstr)
{
  GUID *v9; // rcx
  unsigned int Instance; // eax
  LPWSTR v11; // rdi
  const WCHAR *i; // rax
  unsigned int ClassObject; // edi
  const OLECHAR *v14; // rcx
  HRESULT v15; // eax
  LPVOID v16; // [rsp+40h] [rbp-48h] BYREF
  CLSID pclsid; // [rsp+48h] [rbp-40h] BYREF

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  pclsid = 0;
  *a4 = 0;
  if ( a1 && *a1 )
  {
    if ( ((*a1 - 77) & 0xFFDF) != 0
      || ((a1[1] - 83) & 0xFFDF) != 0
      || ((a1[2] - 72) & 0xFFDF) != 0
      || ((a1[3] - 84) & 0xFFDF) != 0
      || ((a1[4] - 77) & 0xFFDF) != 0
      || ((a1[5] - 76) & 0xFFDF) != 0
      || a1[6] != 58 )
    {
      v11 = a1;
LABEL_15:
      if ( !v11 || !*v11 )
        goto LABEL_25;
      for ( i = L":"; ; i = CharNextW(i) )
      {
        if ( !i || !*i )
        {
          v11 = CharNextW(v11);
          goto LABEL_15;
        }
        if ( *v11 == *i )
          break;
      }
      if ( !CharNextW(v11) )
      {
LABEL_25:
        ClassObject = -2147467259;
        if ( (int)ocslen(a1) >= 255 )
          return ClassObject;
        v15 = *a1 == 123 ? CLSIDFromString(v14, &pclsid) : CLSIDFromProgID(v14, &pclsid);
        ClassObject = v15;
        if ( v15 < 0 )
          return ClassObject;
        if ( SysStringLen(pbstr) )
        {
          v16 = 0;
          ClassObject = CoGetClassObject(&pclsid, 1u, 0, &GUID_b196b28f_bab4_101a_b69c_00aa00341d07, &v16);
          if ( (ClassObject & 0x80000000) == 0 )
            ClassObject = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, GUID *, BSTR, LPVOID *))(*(_QWORD *)v16 + 56LL))(
                            v16,
                            0,
                            0,
                            &GUID_00000000_0000_0000_c000_000000000046,
                            pbstr,
                            a3);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v16);
          return ClassObject;
        }
        return (unsigned int)CoCreateInstance(&pclsid, 0, 1u, &GUID_00000000_0000_0000_c000_000000000046, a3);
      }
      v9 = &GUID_8856f961_340a_11d0_a96b_00c04fd705a2;
    }
    else
    {
      v9 = &GUID_25336920_03f9_11cf_8fd0_00aa00686f13;
    }
    Instance = CoCreateInstance(v9, 0, 1u, &GUID_00000000_0000_0000_c000_000000000046, a3);
    *a4 = 1;
    return Instance;
  }
  return 0;
}

```

## disassembly

```asm
0x18001585c  mov     [rsp+arg_8], rbx
0x180015861  push    rbp
0x180015862  push    rsi
0x180015863  push    rdi
0x180015864  push    r14
0x180015866  push    r15
0x180015868  sub     rsp, 60h
0x18001586c  mov     rax, cs:__security_cookie
0x180015873  xor     rax, rsp
0x180015876  mov     [rsp+88h+var_30], rax
0x18001587b  mov     r14, r9
0x18001587e  mov     rsi, r8
0x180015881  mov     rbx, rcx
0x180015884  mov     rbp, [rsp+88h+pbstr]
0x18001588c  xor     r15d, r15d
0x18001588f  test    r8, r8
0x180015892  jnz     short loc_18001589E
0x180015894  mov     eax, 80004003h
0x180015899  jmp     loc_180015A68
0x18001589e  mov     [r8], r15
0x1800158a1  xorps   xmm0, xmm0
0x1800158a4  movups  xmmword ptr [rsp+88h+pclsid.Data1], xmm0
0x1800158a9  mov     [r9], r15b
0x1800158ac  test    rbx, rbx
0x1800158af  jz      loc_180015A66
0x1800158b5  movzx   eax, word ptr [rcx]
0x1800158b8  test    ax, ax
0x1800158bb  jz      loc_180015A66
0x1800158c1  sub     ax, 4Dh ; 'M'
0x1800158c5  mov     ecx, 0FFDFh
0x1800158ca  test    cx, ax
0x1800158cd  jnz     short loc_180015941
0x1800158cf  movzx   eax, word ptr [rbx+2]
0x1800158d3  sub     ax, 53h ; 'S'
0x1800158d7  test    cx, ax
0x1800158da  jnz     short loc_180015941
0x1800158dc  movzx   eax, word ptr [rbx+4]
0x1800158e0  sub     ax, 48h ; 'H'
0x1800158e4  test    cx, ax
0x1800158e7  jnz     short loc_180015941
0x1800158e9  movzx   eax, word ptr [rbx+6]
0x1800158ed  sub     ax, 54h ; 'T'
0x1800158f1  test    cx, ax
0x1800158f4  jnz     short loc_180015941
0x1800158f6  movzx   eax, word ptr [rbx+8]
0x1800158fa  sub     ax, 4Dh ; 'M'
0x1800158fe  test    cx, ax
0x180015901  jnz     short loc_180015941
0x180015903  movzx   eax, word ptr [rbx+0Ah]
0x180015907  sub     ax, 4Ch ; 'L'
0x18001590b  test    cx, ax
0x18001590e  jnz     short loc_180015941
0x180015910  cmp     word ptr [rbx+0Ch], 3Ah ; ':'
0x180015915  jnz     short loc_180015941
0x180015917  lea     rcx, _GUID_25336920_03f9_11cf_8fd0_00aa00686f13; rclsid
0x18001591e  mov     r8d, 1; dwClsContext
0x180015924  xor     edx, edx; pUnkOuter
0x180015926  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18001592d  mov     [rsp+88h+ppv], rsi; ppv
0x180015932  call    cs:__imp_CoCreateInstance
0x180015938  mov     byte ptr [r14], 1
0x18001593c  jmp     loc_180015A60
0x180015941  mov     rdi, rbx
0x180015944  test    rdi, rdi
0x180015947  jz      short loc_180015998
0x180015949  cmp     [rdi], r15w
0x18001594d  jz      short loc_180015998
0x18001594f  lea     rax, sz; ":"
0x180015956  test    rax, rax
0x180015959  jz      short loc_180015973
0x18001595b  movzx   ecx, word ptr [rax]
0x18001595e  test    cx, cx
0x180015961  jz      short loc_180015973
0x180015963  cmp     [rdi], cx
0x180015966  jz      short loc_180015981
0x180015968  mov     rcx, rax; lpsz
0x18001596b  call    cs:__imp_CharNextW
0x180015971  jmp     short loc_180015956
0x180015973  mov     rcx, rdi; lpsz
0x180015976  call    cs:__imp_CharNextW
0x18001597c  mov     rdi, rax
0x18001597f  jmp     short loc_180015944
0x180015981  mov     rcx, rdi; lpsz
0x180015984  call    cs:__imp_CharNextW
0x18001598a  test    rax, rax
0x18001598d  jz      short loc_180015998
0x18001598f  lea     rcx, _GUID_8856f961_340a_11d0_a96b_00c04fd705a2
0x180015996  jmp     short loc_18001591E
0x180015998  mov     edi, 80004005h
0x18001599d  mov     rcx, rbx; unsigned __int16 *
0x1800159a0  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x1800159a5  cmp     eax, 0FFh
0x1800159aa  jge     loc_180015A62
0x1800159b0  lea     rdx, [rsp+88h+pclsid]; lpclsid
0x1800159b5  cmp     word ptr [rbx], 7Bh ; '{'
0x1800159b9  jnz     short loc_1800159C3
0x1800159bb  call    cs:__imp_CLSIDFromString
0x1800159c1  jmp     short loc_1800159C9
0x1800159c3  call    cs:__imp_CLSIDFromProgID
0x1800159c9  mov     edi, eax
0x1800159cb  test    eax, eax
0x1800159cd  js      loc_180015A62
0x1800159d3  mov     rcx, rbp; pbstr
0x1800159d6  call    cs:__imp_SysStringLen
0x1800159dc  test    eax, eax
0x1800159de  jz      short loc_180015A43
0x1800159e0  mov     [rsp+88h+var_48], r15
0x1800159e5  lea     rax, [rsp+88h+var_48]
0x1800159ea  mov     [rsp+88h+ppv], rax; ppv
0x1800159ef  lea     r9, _GUID_b196b28f_bab4_101a_b69c_00aa00341d07; riid
0x1800159f6  xor     r8d, r8d; pvReserved
0x1800159f9  lea     edx, [r8+1]; dwClsContext
0x1800159fd  lea     rcx, [rsp+88h+pclsid]; rclsid
0x180015a02  call    cs:__imp_CoGetClassObject
0x180015a08  mov     edi, eax
0x180015a0a  test    eax, eax
0x180015a0c  js      short loc_180015A37
0x180015a0e  mov     rcx, [rsp+88h+var_48]
0x180015a13  mov     rax, [rcx]
0x180015a16  mov     [rsp+88h+var_60], rsi
0x180015a1b  mov     [rsp+88h+ppv], rbp
0x180015a20  lea     r9, _GUID_00000000_0000_0000_c000_000000000046
0x180015a27  xor     r8d, r8d
0x180015a2a  xor     edx, edx
0x180015a2c  mov     rax, [rax+38h]
0x180015a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a35  mov     edi, eax
0x180015a37  lea     rcx, [rsp+88h+var_48]
0x180015a3c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180015a41  jmp     short loc_180015A62
0x180015a43  mov     [rsp+88h+ppv], rsi; ppv
0x180015a48  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180015a4f  xor     edx, edx; pUnkOuter
0x180015a51  lea     r8d, [rdx+1]; dwClsContext
0x180015a55  lea     rcx, [rsp+88h+pclsid]; rclsid
0x180015a5a  call    cs:__imp_CoCreateInstance
0x180015a60  mov     edi, eax
0x180015a62  mov     eax, edi
0x180015a64  jmp     short loc_180015A68
0x180015a66  xor     eax, eax
0x180015a68  mov     rcx, [rsp+88h+var_30]
0x180015a6d  xor     rcx, rsp; StackCookie
0x180015a70  call    __security_check_cookie
0x180015a75  mov     rbx, [rsp+88h+arg_8]
0x180015a7d  add     rsp, 60h
0x180015a81  pop     r15
0x180015a83  pop     r14
0x180015a85  pop     rdi
0x180015a86  pop     rsi
0x180015a87  pop     rbp
0x180015a88  retn
```
