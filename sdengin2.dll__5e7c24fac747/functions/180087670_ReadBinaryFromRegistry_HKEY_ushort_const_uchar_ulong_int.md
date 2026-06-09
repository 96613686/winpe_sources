# ReadBinaryFromRegistry(HKEY__ *,ushort const *,uchar * *,ulong *,int)

- ea: `0x180087670`
- end: `0x18008783a`
- name: `?ReadBinaryFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAKH@Z`
- size: `458`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, const unsigned __int16 *@<rdx>, unsigned __int8 **@<r8>, unsigned int *@<r9>, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18008cf94`

## callees

- `0x18006fe84`
- `0x18006ff8c`
- `0x180087670`
- `0x1800c97da`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008772b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800877ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008772b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800877ca`
- `ole32!CoTaskMemFree` at `0x180087806`
- `ole32!CoTaskMemFree` at `0x180087806`
- `ole32!CoTaskMemAlloc` at `0x180087775`
- `ole32!CoTaskMemAlloc` at `0x180087775`

## string_xrefs

- `0x180087687`: `ReadBinaryFromRegistry`

## pseudocode

```c
__int64 __fastcall ReadBinaryFromRegistry(
        HKEY hKey,
        const unsigned __int16 *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        DWORD cbData)
{
  __int16 v8; // ax
  signed int v9; // ebx
  LSTATUS v10; // eax
  __int16 v11; // ax
  void *lpData; // rdi
  int v13; // eax
  bool v14; // sf
  unsigned int v15; // ecx
  int v17; // [rsp+30h] [rbp-48h] BYREF
  __int16 v18; // [rsp+34h] [rbp-44h]
  __int16 v19; // [rsp+36h] [rbp-42h]
  int v20; // [rsp+38h] [rbp-40h]
  const unsigned __int16 *Type; // [rsp+B8h] [rbp+40h] BYREF

  Type = a2;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "ReadBinaryFromRegistry", 332, 2);
  LODWORD(Type) = 0;
  cbData = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v18 = 342;
  v8 = 343;
  if ( !a3 || (v18 = 343, v8 = 344, !a4) )
  {
    v9 = -2147024809;
LABEL_7:
    v19 = v8;
LABEL_25:
    v17 = v9;
    goto LABEL_26;
  }
  v18 = 344;
  v17 = 0;
  v10 = RegQueryValueExW(hKey, L"Sid", 0, (LPDWORD)&Type, 0, &cbData);
  v9 = v10;
  if ( v10 == 2 )
  {
    v9 = 1;
    v11 = 349;
LABEL_24:
    v18 = v11;
    goto LABEL_25;
  }
  if ( v10 > 0 )
    v9 = (unsigned __int16)v10 | 0x80070000;
  v17 = v9;
  if ( v9 < 0 )
  {
    v19 = 352;
    v20 = 1;
    goto LABEL_26;
  }
  v18 = 352;
  lpData = CoTaskMemAlloc(cbData);
  v8 = 355;
  if ( !lpData )
  {
    v9 = -2147024882;
    goto LABEL_7;
  }
  v17 = 0;
  v18 = 355;
  memset_0(lpData, 0, cbData);
  v13 = RegQueryValueExW(hKey, L"Sid", 0, (LPDWORD)&Type, (LPBYTE)lpData, &cbData);
  if ( v13 > 0 )
    v13 = (unsigned __int16)v13 | 0x80070000;
  v17 = v13;
  v14 = v13 < 0;
  v11 = 359;
  if ( !v14 )
  {
    v18 = 359;
    v11 = 360;
    if ( (_DWORD)Type == 3 )
    {
      v15 = cbData;
      v9 = 0;
      *a3 = (unsigned __int8 *)lpData;
      *a4 = v15;
      goto LABEL_24;
    }
    v17 = -2147024809;
  }
  v19 = v11;
  CoTaskMemFree(lpData);
  v9 = v17;
LABEL_26:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180087670  mov     [rsp-30h+Type], rdx
0x180087675  push    rbp
0x180087676  push    rbx
0x180087677  push    rsi
0x180087678  push    rdi
0x180087679  push    r14
0x18008767b  push    r15
0x18008767d  mov     rbp, rsp
0x180087680  sub     rsp, 78h
0x180087684  mov     rsi, r9
0x180087687  lea     rdx, aReadbinaryfrom; "ReadBinaryFromRegistry"
0x18008768e  mov     r14, r8
0x180087691  mov     r15, rcx
0x180087694  mov     r9d, 2; unsigned __int16
0x18008769a  lea     rcx, [rbp+var_48]; this
0x18008769e  mov     r8d, 14Ch; unsigned __int16
0x1800876a4  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800876a9  mov     dword ptr [rbp+Type], 0
0x1800876b0  mov     [rbp+cbData], 0
0x1800876b7  test    r14, r14
0x1800876ba  jz      short loc_1800876C3
0x1800876bc  mov     qword ptr [r14], 0
0x1800876c3  test    rsi, rsi
0x1800876c6  jz      short loc_1800876CE
0x1800876c8  mov     dword ptr [rsi], 0
0x1800876ce  mov     eax, 156h
0x1800876d3  mov     [rbp+var_44], ax
0x1800876d7  mov     eax, 157h
0x1800876dc  test    r14, r14
0x1800876df  jnz     short loc_1800876EF
0x1800876e1  mov     ebx, 80070057h
0x1800876e6  mov     [rbp+var_42], ax
0x1800876ea  jmp     loc_18008781F
0x1800876ef  mov     [rbp+var_44], ax
0x1800876f3  mov     eax, 158h
0x1800876f8  test    rsi, rsi
0x1800876fb  jz      short loc_1800876E1
0x1800876fd  mov     [rbp+var_44], ax
0x180087701  lea     r9, [rbp+Type]; lpType
0x180087705  lea     rax, [rbp+cbData]
0x180087709  mov     [rbp+var_48], 0
0x180087710  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180087715  lea     rdx, ValueName; "Sid"
0x18008771c  xor     r8d, r8d; lpReserved
0x18008771f  mov     [rsp+78h+lpData], 0; lpData
0x180087728  mov     rcx, r15; hKey
0x18008772b  call    cs:__imp_RegQueryValueExW
0x180087731  mov     ebx, eax
0x180087733  cmp     eax, 2
0x180087736  jnz     short loc_180087745
0x180087738  lea     ebx, [rax-1]
0x18008773b  mov     eax, 15Dh
0x180087740  jmp     loc_18008781B
0x180087745  test    eax, eax
0x180087747  jle     short loc_180087752
0x180087749  movzx   ebx, ax
0x18008774c  or      ebx, 80070000h
0x180087752  mov     [rbp+var_48], ebx
0x180087755  mov     eax, 160h
0x18008775a  test    ebx, ebx
0x18008775c  jns     short loc_18008776E
0x18008775e  mov     [rbp+var_42], ax
0x180087762  mov     [rbp+var_40], 1
0x180087769  jmp     loc_180087822
0x18008776e  mov     ecx, [rbp+cbData]; cb
0x180087771  mov     [rbp+var_44], ax
0x180087775  call    cs:__imp_CoTaskMemAlloc
0x18008777b  mov     rdi, rax
0x18008777e  test    rax, rax
0x180087781  mov     eax, 163h
0x180087786  jnz     short loc_180087792
0x180087788  mov     ebx, 8007000Eh
0x18008778d  jmp     loc_1800876E6
0x180087792  mov     r8d, [rbp+cbData]; Size
0x180087796  xor     edx, edx; Val
0x180087798  mov     rcx, rdi; void *
0x18008779b  mov     [rbp+var_48], 0
0x1800877a2  mov     [rbp+var_44], ax
0x1800877a6  call    memset_0
0x1800877ab  lea     rax, [rbp+cbData]
0x1800877af  xor     r8d, r8d; lpReserved
0x1800877b2  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800877b7  lea     r9, [rbp+Type]; lpType
0x1800877bb  lea     rdx, ValueName; "Sid"
0x1800877c2  mov     [rsp+78h+lpData], rdi; lpData
0x1800877c7  mov     rcx, r15; hKey
0x1800877ca  call    cs:__imp_RegQueryValueExW
0x1800877d0  test    eax, eax
0x1800877d2  jle     short loc_1800877DC
0x1800877d4  movzx   eax, ax
0x1800877d7  or      eax, 80070000h
0x1800877dc  mov     [rbp+var_48], eax
0x1800877df  test    eax, eax
0x1800877e1  mov     eax, 167h
0x1800877e6  js      short loc_1800877FF
0x1800877e8  cmp     dword ptr [rbp+Type], 3
0x1800877ec  mov     [rbp+var_44], ax
0x1800877f0  mov     eax, 168h
0x1800877f5  jz      short loc_180087811
0x1800877f7  mov     ebx, 80070057h
0x1800877fc  mov     [rbp+var_48], ebx
0x1800877ff  mov     rcx, rdi; pv
0x180087802  mov     [rbp+var_42], ax
0x180087806  call    cs:__imp_CoTaskMemFree
0x18008780c  mov     ebx, [rbp+var_48]
0x18008780f  jmp     short loc_180087822
0x180087811  mov     ecx, [rbp+cbData]
0x180087814  xor     ebx, ebx
0x180087816  mov     [r14], rdi
0x180087819  mov     [rsi], ecx
0x18008781b  mov     [rbp+var_44], ax
0x18008781f  mov     [rbp+var_48], ebx
0x180087822  lea     rcx, [rbp+var_48]; this
0x180087826  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008782b  mov     eax, ebx
0x18008782d  add     rsp, 78h
0x180087831  pop     r15
0x180087833  pop     r14
0x180087835  pop     rdi
0x180087836  pop     rsi
0x180087837  pop     rbx
0x180087838  pop     rbp
0x180087839  retn
```
