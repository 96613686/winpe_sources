# DeleteBlbBackupSets(_DELETE_BACKUP_INFO *)

- ea: `0x18008ee80`
- end: `0x18008f112`
- name: `?DeleteBlbBackupSets@@YAJPEAU_DELETE_BACKUP_INFO@@@Z`
- size: `658`
- prototype: `__int64 __fastcall(struct _DELETE_BACKUP_INFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180040d70`

## callees

- `0x180003520`
- `0x180003534`
- `0x1800083a0`
- `0x180072e08`
- `0x180072f14`
- `0x18008ed44`
- `0x18008ee80`
- `0x18008f118`
- `0x1800d1010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18008efef`
- `msvcrt!_wcsicmp` at `0x18008efef`
- `KERNEL32!CompareFileTime` at `0x18008f00f`
- `KERNEL32!CompareFileTime` at `0x18008f00f`
- `ole32!CoCreateInstance` at `0x18008ef1b`
- `ole32!CoCreateInstance` at `0x18008ef1b`

## string_xrefs

- `0x18008ee9c`: `DeleteBlbBackupSets`

## pseudocode

```c
__int64 __fastcall DeleteBlbBackupSets(struct _FILETIME *a1)
{
  bool v2; // zf
  __int16 v3; // ax
  __int16 v4; // ax
  unsigned int v5; // ecx
  bool v6; // r15
  unsigned int v7; // r14d
  struct _BLB_BACKUP_SET_INFO *v8; // rsi
  __int64 v9; // rdi
  __int64 v10; // r8
  __int64 v11; // rax
  int v12; // eax
  unsigned int v13; // ebx
  __int128 v15; // [rsp+30h] [rbp-50h] BYREF
  HRESULT v16; // [rsp+40h] [rbp-40h] BYREF
  __int16 v17; // [rsp+44h] [rbp-3Ch]
  __int16 v18; // [rsp+46h] [rbp-3Ah]
  unsigned int v19; // [rsp+B0h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+B8h] [rbp+38h] BYREF
  struct _BLB_BACKUP_SET_INFO *v21; // [rsp+C0h] [rbp+40h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "DeleteBlbBackupSets", 0x2Fu, 1u);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&ppv);
  v19 = 0;
  v21 = 0;
  if ( !a1 )
  {
    v16 = -2147024809;
    v18 = 58;
    goto LABEL_31;
  }
  v2 = a1[2].dwLowDateTime == 0;
  v16 = 0;
  v17 = 58;
  if ( !v2 && !a1[2].dwHighDateTime )
  {
    v17 = 64;
    goto LABEL_31;
  }
  v16 = CoCreateInstance(&CLSID_BlbEngine, 0, 4u, &IID_IBlbEngine, &ppv);
  v3 = 68;
  if ( v16 < 0 || (v17 = 68, v16 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 24LL))(ppv), v3 = 70, v16 < 0) )
  {
    v18 = v3;
    goto LABEL_28;
  }
  v17 = 70;
  v16 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *, struct _BLB_BACKUP_SET_INFO **))(*(_QWORD *)ppv + 208LL))(
          ppv,
          &v19,
          &v21);
  v4 = 73;
  if ( v16 >= 0 )
  {
    v5 = v19;
    v17 = 73;
    if ( v19 )
    {
      v6 = a1[2].dwLowDateTime == 0;
      v7 = 0;
      do
      {
        v8 = v21;
        v9 = 168LL * v7;
        if ( *((_BYTE *)v21 + v9 + 112) && ((*(_DWORD *)((char *)v21 + v9 + 28) - 1) & 0xFFFFFFFB) != 0 )
        {
          if ( !_wcsicmp(*(const wchar_t **)(*(_QWORD *)((char *)v21 + v9 + 32) + 16LL), *(const wchar_t **)a1)
            && (a1[2].dwHighDateTime || CompareFileTime((const FILETIME *)((char *)v8 + v9 + 88), a1 + 3) < 0) )
          {
            LOBYTE(v10) = v6;
            v11 = *(_QWORD *)ppv;
            v15 = *(_OWORD *)((char *)v8 + v9);
            v12 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int64))(v11 + 304))(ppv, &v15, v10);
            if ( v12 < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                10,
                WPP_d3161b922d5834647e966e945bbffc28_Traceguids,
                (unsigned int)v12);
            }
          }
          v5 = v19;
        }
        ++v7;
      }
      while ( v7 < v5 );
      if ( a1[2].dwLowDateTime )
        goto LABEL_27;
      v16 = DeleteVssSnapshots(*(wchar_t **)a1, a1[2].dwHighDateTime, a1 + 3);
      v4 = 123;
      if ( v16 < 0 )
        goto LABEL_9;
    }
    else
    {
      v16 = 0;
      v4 = 77;
    }
    v17 = v4;
    goto LABEL_27;
  }
LABEL_9:
  v18 = v4;
LABEL_27:
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
LABEL_28:
  if ( v21 )
    FreeBlbBackupSetArray(&v21, &v19);
LABEL_31:
  v13 = v16;
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>(&ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return v13;
}

```

## disassembly

```asm
0x18008ee80  mov     [rsp-28h+arg_18], rbx
0x18008ee85  push    rbp
0x18008ee86  push    rsi
0x18008ee87  push    rdi
0x18008ee88  push    r14
0x18008ee8a  push    r15
0x18008ee8c  mov     rbp, rsp
0x18008ee8f  sub     rsp, 80h
0x18008ee96  mov     r9d, 1; unsigned __int16
0x18008ee9c  lea     rdx, aDeleteblbbacku; "DeleteBlbBackupSets"
0x18008eea3  mov     rbx, rcx
0x18008eea6  lea     rcx, [rbp+var_40]; this
0x18008eeaa  lea     r8d, [r9+2Eh]; unsigned __int16
0x18008eeae  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008eeb3  lea     rcx, [rbp+arg_8]; void *
0x18008eeb7  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18008eebc  mov     [rbp+arg_0], 0
0x18008eec3  mov     eax, 3Ah ; ':'
0x18008eec8  mov     [rbp+arg_10], 0
0x18008eed0  test    rbx, rbx
0x18008eed3  jz      loc_18008F0D8
0x18008eed9  cmp     dword ptr [rbx+10h], 0
0x18008eedd  mov     [rbp+var_40], 0
0x18008eee4  mov     [rbp+var_3C], ax
0x18008eee8  jz      short loc_18008EEFE
0x18008eeea  cmp     dword ptr [rbx+14h], 0
0x18008eeee  jnz     short loc_18008EEFE
0x18008eef0  mov     eax, 40h ; '@'
0x18008eef5  mov     [rbp+var_3C], ax
0x18008eef9  jmp     loc_18008F0E3
0x18008eefe  xor     edx, edx; pUnkOuter
0x18008ef00  lea     rax, [rbp+arg_8]
0x18008ef04  lea     r9, IID_IBlbEngine; riid
0x18008ef0b  mov     [rsp+80h+ppv], rax; ppv
0x18008ef10  lea     rcx, CLSID_BlbEngine; rclsid
0x18008ef17  lea     r8d, [rdx+4]; dwClsContext
0x18008ef1b  call    cs:__imp_CoCreateInstance
0x18008ef22  nop     dword ptr [rax+rax+00h]
0x18008ef27  mov     [rbp+var_40], eax
0x18008ef2a  test    eax, eax
0x18008ef2c  mov     eax, 44h ; 'D'
0x18008ef31  jns     short loc_18008EF3C
0x18008ef33  mov     [rbp+var_3A], ax
0x18008ef37  jmp     loc_18008F0C2
0x18008ef3c  mov     rcx, [rbp+arg_8]
0x18008ef40  mov     [rbp+var_3C], ax
0x18008ef44  mov     rax, [rcx]
0x18008ef47  mov     rax, [rax+18h]
0x18008ef4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ef50  mov     [rbp+var_40], eax
0x18008ef53  test    eax, eax
0x18008ef55  mov     eax, 46h ; 'F'
0x18008ef5a  js      short loc_18008EF33
0x18008ef5c  mov     rcx, [rbp+arg_8]
0x18008ef60  lea     r8, [rbp+arg_10]
0x18008ef64  mov     [rbp+var_3C], ax
0x18008ef68  lea     rdx, [rbp+arg_0]
0x18008ef6c  mov     rax, [rcx]
0x18008ef6f  mov     rax, [rax+0D0h]
0x18008ef76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ef7b  mov     [rbp+var_40], eax
0x18008ef7e  test    eax, eax
0x18008ef80  mov     eax, 49h ; 'I'
0x18008ef85  jns     short loc_18008EF90
0x18008ef87  mov     [rbp+var_3A], ax
0x18008ef8b  jmp     loc_18008F0B2
0x18008ef90  mov     ecx, [rbp+arg_0]
0x18008ef93  mov     [rbp+var_3C], ax
0x18008ef97  test    ecx, ecx
0x18008ef99  jnz     short loc_18008EFA6
0x18008ef9b  mov     [rbp+var_40], ecx
0x18008ef9e  lea     eax, [rcx+4Dh]
0x18008efa1  jmp     loc_18008F0AE
0x18008efa6  cmp     dword ptr [rbx+10h], 0
0x18008efaa  setz    r15b
0x18008efae  xor     r14d, r14d
0x18008efb1  test    ecx, ecx
0x18008efb3  jz      loc_18008F089
0x18008efb9  mov     rsi, [rbp+arg_10]
0x18008efbd  mov     eax, r14d
0x18008efc0  imul    rdi, rax, 0A8h
0x18008efc7  cmp     byte ptr [rdi+rsi+70h], 0
0x18008efcc  jz      loc_18008F07D
0x18008efd2  mov     eax, [rdi+rsi+1Ch]
0x18008efd6  dec     eax
0x18008efd8  test    eax, 0FFFFFFFBh
0x18008efdd  jz      loc_18008F07D
0x18008efe3  mov     rcx, [rdi+rsi+20h]
0x18008efe8  mov     rdx, [rbx]; String2
0x18008efeb  mov     rcx, [rcx+10h]; String1
0x18008efef  call    cs:__imp__wcsicmp
0x18008eff6  nop     dword ptr [rax+rax+00h]
0x18008effb  test    eax, eax
0x18008effd  jnz     short loc_18008F07A
0x18008efff  cmp     [rbx+14h], eax
0x18008f002  jnz     short loc_18008F01F
0x18008f004  lea     rcx, [rsi+58h]
0x18008f008  add     rcx, rdi; lpFileTime1
0x18008f00b  lea     rdx, [rbx+18h]; lpFileTime2
0x18008f00f  call    cs:__imp_CompareFileTime
0x18008f016  nop     dword ptr [rax+rax+00h]
0x18008f01b  test    eax, eax
0x18008f01d  jns     short loc_18008F07A
0x18008f01f  mov     rcx, [rbp+arg_8]
0x18008f023  lea     rdx, [rbp+var_50]
0x18008f027  movups  xmm0, xmmword ptr [rdi+rsi]
0x18008f02b  mov     r8b, r15b
0x18008f02e  mov     rax, [rcx]
0x18008f031  movdqu  [rbp+var_50], xmm0
0x18008f036  mov     rax, [rax+130h]
0x18008f03d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f042  test    eax, eax
0x18008f044  jns     short loc_18008F07A
0x18008f046  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f04d  lea     rdx, WPP_GLOBAL_Control
0x18008f054  cmp     rcx, rdx
0x18008f057  jz      short loc_18008F07A
0x18008f059  test    dword ptr [rcx+1Ch], 200h
0x18008f060  jz      short loc_18008F07A
0x18008f062  mov     rcx, [rcx+10h]
0x18008f066  lea     r8, WPP_d3161b922d5834647e966e945bbffc28_Traceguids
0x18008f06d  mov     edx, 0Ah
0x18008f072  mov     r9d, eax
0x18008f075  call    WPP_SF_d
0x18008f07a  mov     ecx, [rbp+arg_0]
0x18008f07d  inc     r14d
0x18008f080  cmp     r14d, ecx
0x18008f083  jb      loc_18008EFB9
0x18008f089  cmp     dword ptr [rbx+10h], 0
0x18008f08d  jnz     short loc_18008F0B2
0x18008f08f  mov     edx, [rbx+14h]; int
0x18008f092  lea     r8, [rbx+18h]; struct _FILETIME *
0x18008f096  mov     rcx, [rbx]; String1
0x18008f099  call    ?DeleteVssSnapshots@@YAJPEBGHPEAU_FILETIME@@@Z; DeleteVssSnapshots(ushort const *,int,_FILETIME *)
0x18008f09e  mov     [rbp+var_40], eax
0x18008f0a1  test    eax, eax
0x18008f0a3  mov     eax, 7Bh ; '{'
0x18008f0a8  js      loc_18008EF87
0x18008f0ae  mov     [rbp+var_3C], ax
0x18008f0b2  mov     rcx, [rbp+arg_8]
0x18008f0b6  mov     rax, [rcx]
0x18008f0b9  mov     rax, [rax+20h]
0x18008f0bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f0c2  cmp     [rbp+arg_10], 0
0x18008f0c7  jz      short loc_18008F0E3
0x18008f0c9  lea     rdx, [rbp+arg_0]; unsigned int *
0x18008f0cd  lea     rcx, [rbp+arg_10]; struct _BLB_BACKUP_SET_INFO **
0x18008f0d1  call    ?FreeBlbBackupSetArray@@YAXPEAPEAU_BLB_BACKUP_SET_INFO@@PEAK@Z; FreeBlbBackupSetArray(_BLB_BACKUP_SET_INFO * *,ulong *)
0x18008f0d6  jmp     short loc_18008F0E3
0x18008f0d8  mov     [rbp+var_40], 80070057h
0x18008f0df  mov     [rbp+var_3A], ax
0x18008f0e3  mov     ebx, [rbp+var_40]
0x18008f0e6  lea     rcx, [rbp+arg_8]
0x18008f0ea  call    ??1?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>(void)
0x18008f0ef  lea     rcx, [rbp+var_40]; this
0x18008f0f3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008f0f8  mov     eax, ebx
0x18008f0fa  mov     rbx, [rsp+80h+arg_18]
0x18008f102  add     rsp, 80h
0x18008f109  pop     r15
0x18008f10b  pop     r14
0x18008f10d  pop     rdi
0x18008f10e  pop     rsi
0x18008f10f  pop     rbp
0x18008f110  retn
```
