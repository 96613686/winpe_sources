# DeleteBlbBackupSets(_DELETE_BACKUP_INFO *)

- ea: `0x18008b108`
- end: `0x18008b387`
- name: `?DeleteBlbBackupSets@@YAJPEAU_DELETE_BACKUP_INFO@@@Z`
- size: `639`
- prototype: `__int64 __fastcall(struct _DELETE_BACKUP_INFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003f5cc`

## callees

- `0x180003430`
- `0x180003444`
- `0x180008200`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008afdc`
- `0x18008b108`
- `0x18008b390`
- `0x1800cb010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18008b271`
- `msvcrt!_wcsicmp` at `0x18008b271`
- `KERNEL32!CompareFileTime` at `0x18008b28b`
- `KERNEL32!CompareFileTime` at `0x18008b28b`
- `ole32!CoCreateInstance` at `0x18008b1a3`
- `ole32!CoCreateInstance` at `0x18008b1a3`

## string_xrefs

- `0x18008b124`: `DeleteBlbBackupSets`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "DeleteBlbBackupSets", 47, 1);
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
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>((__int64)&ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return v13;
}

```

## disassembly

```asm
0x18008b108  mov     [rsp-28h+arg_18], rbx
0x18008b10d  push    rbp
0x18008b10e  push    rsi
0x18008b10f  push    rdi
0x18008b110  push    r14
0x18008b112  push    r15
0x18008b114  mov     rbp, rsp
0x18008b117  sub     rsp, 80h
0x18008b11e  mov     r9d, 1; unsigned __int16
0x18008b124  lea     rdx, aDeleteblbbacku; "DeleteBlbBackupSets"
0x18008b12b  mov     rbx, rcx
0x18008b12e  lea     rcx, [rbp+var_40]; this
0x18008b132  lea     r8d, [r9+2Eh]; unsigned __int16
0x18008b136  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008b13b  lea     rcx, [rbp+arg_8]; void *
0x18008b13f  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18008b144  mov     [rbp+arg_0], 0
0x18008b14b  mov     eax, 3Ah ; ':'
0x18008b150  mov     [rbp+arg_10], 0
0x18008b158  test    rbx, rbx
0x18008b15b  jz      loc_18008B34E
0x18008b161  cmp     dword ptr [rbx+10h], 0
0x18008b165  mov     [rbp+var_40], 0
0x18008b16c  mov     [rbp+var_3C], ax
0x18008b170  jz      short loc_18008B186
0x18008b172  cmp     dword ptr [rbx+14h], 0
0x18008b176  jnz     short loc_18008B186
0x18008b178  mov     eax, 40h ; '@'
0x18008b17d  mov     [rbp+var_3C], ax
0x18008b181  jmp     loc_18008B359
0x18008b186  xor     edx, edx; pUnkOuter
0x18008b188  lea     rax, [rbp+arg_8]
0x18008b18c  lea     r9, IID_IBlbEngine; riid
0x18008b193  mov     [rsp+80h+ppv], rax; ppv
0x18008b198  lea     rcx, CLSID_BlbEngine; rclsid
0x18008b19f  lea     r8d, [rdx+4]; dwClsContext
0x18008b1a3  call    cs:__imp_CoCreateInstance
0x18008b1a9  mov     [rbp+var_40], eax
0x18008b1ac  test    eax, eax
0x18008b1ae  mov     eax, 44h ; 'D'
0x18008b1b3  jns     short loc_18008B1BE
0x18008b1b5  mov     [rbp+var_3A], ax
0x18008b1b9  jmp     loc_18008B338
0x18008b1be  mov     rcx, [rbp+arg_8]
0x18008b1c2  mov     [rbp+var_3C], ax
0x18008b1c6  mov     rax, [rcx]
0x18008b1c9  mov     rax, [rax+18h]
0x18008b1cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b1d2  mov     [rbp+var_40], eax
0x18008b1d5  test    eax, eax
0x18008b1d7  mov     eax, 46h ; 'F'
0x18008b1dc  js      short loc_18008B1B5
0x18008b1de  mov     rcx, [rbp+arg_8]
0x18008b1e2  lea     r8, [rbp+arg_10]
0x18008b1e6  mov     [rbp+var_3C], ax
0x18008b1ea  lea     rdx, [rbp+arg_0]
0x18008b1ee  mov     rax, [rcx]
0x18008b1f1  mov     rax, [rax+0D0h]
0x18008b1f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b1fd  mov     [rbp+var_40], eax
0x18008b200  test    eax, eax
0x18008b202  mov     eax, 49h ; 'I'
0x18008b207  jns     short loc_18008B212
0x18008b209  mov     [rbp+var_3A], ax
0x18008b20d  jmp     loc_18008B328
0x18008b212  mov     ecx, [rbp+arg_0]
0x18008b215  mov     [rbp+var_3C], ax
0x18008b219  test    ecx, ecx
0x18008b21b  jnz     short loc_18008B228
0x18008b21d  mov     [rbp+var_40], ecx
0x18008b220  lea     eax, [rcx+4Dh]
0x18008b223  jmp     loc_18008B324
0x18008b228  cmp     dword ptr [rbx+10h], 0
0x18008b22c  setz    r15b
0x18008b230  xor     r14d, r14d
0x18008b233  test    ecx, ecx
0x18008b235  jz      loc_18008B2FF
0x18008b23b  mov     rsi, [rbp+arg_10]
0x18008b23f  mov     eax, r14d
0x18008b242  imul    rdi, rax, 0A8h
0x18008b249  cmp     byte ptr [rdi+rsi+70h], 0
0x18008b24e  jz      loc_18008B2F3
0x18008b254  mov     eax, [rdi+rsi+1Ch]
0x18008b258  dec     eax
0x18008b25a  test    eax, 0FFFFFFFBh
0x18008b25f  jz      loc_18008B2F3
0x18008b265  mov     rcx, [rdi+rsi+20h]
0x18008b26a  mov     rdx, [rbx]; String2
0x18008b26d  mov     rcx, [rcx+10h]; String1
0x18008b271  call    cs:__imp__wcsicmp
0x18008b277  test    eax, eax
0x18008b279  jnz     short loc_18008B2F0
0x18008b27b  cmp     [rbx+14h], eax
0x18008b27e  jnz     short loc_18008B295
0x18008b280  lea     rcx, [rsi+58h]
0x18008b284  add     rcx, rdi; lpFileTime1
0x18008b287  lea     rdx, [rbx+18h]; lpFileTime2
0x18008b28b  call    cs:__imp_CompareFileTime
0x18008b291  test    eax, eax
0x18008b293  jns     short loc_18008B2F0
0x18008b295  mov     rcx, [rbp+arg_8]
0x18008b299  lea     rdx, [rbp+var_50]
0x18008b29d  movups  xmm0, xmmword ptr [rdi+rsi]
0x18008b2a1  mov     r8b, r15b
0x18008b2a4  mov     rax, [rcx]
0x18008b2a7  movdqu  [rbp+var_50], xmm0
0x18008b2ac  mov     rax, [rax+130h]
0x18008b2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b2b8  test    eax, eax
0x18008b2ba  jns     short loc_18008B2F0
0x18008b2bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b2c3  lea     rdx, WPP_GLOBAL_Control
0x18008b2ca  cmp     rcx, rdx
0x18008b2cd  jz      short loc_18008B2F0
0x18008b2cf  test    dword ptr [rcx+1Ch], 200h
0x18008b2d6  jz      short loc_18008B2F0
0x18008b2d8  mov     rcx, [rcx+10h]
0x18008b2dc  lea     r8, WPP_d3161b922d5834647e966e945bbffc28_Traceguids
0x18008b2e3  mov     edx, 0Ah
0x18008b2e8  mov     r9d, eax
0x18008b2eb  call    WPP_SF_d
0x18008b2f0  mov     ecx, [rbp+arg_0]
0x18008b2f3  inc     r14d
0x18008b2f6  cmp     r14d, ecx
0x18008b2f9  jb      loc_18008B23B
0x18008b2ff  cmp     dword ptr [rbx+10h], 0
0x18008b303  jnz     short loc_18008B328
0x18008b305  mov     edx, [rbx+14h]; int
0x18008b308  lea     r8, [rbx+18h]; struct _FILETIME *
0x18008b30c  mov     rcx, [rbx]; String1
0x18008b30f  call    ?DeleteVssSnapshots@@YAJPEBGHPEAU_FILETIME@@@Z; DeleteVssSnapshots(ushort const *,int,_FILETIME *)
0x18008b314  mov     [rbp+var_40], eax
0x18008b317  test    eax, eax
0x18008b319  mov     eax, 7Bh ; '{'
0x18008b31e  js      loc_18008B209
0x18008b324  mov     [rbp+var_3C], ax
0x18008b328  mov     rcx, [rbp+arg_8]
0x18008b32c  mov     rax, [rcx]
0x18008b32f  mov     rax, [rax+20h]
0x18008b333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b338  cmp     [rbp+arg_10], 0
0x18008b33d  jz      short loc_18008B359
0x18008b33f  lea     rdx, [rbp+arg_0]; unsigned int *
0x18008b343  lea     rcx, [rbp+arg_10]; struct _BLB_BACKUP_SET_INFO **
0x18008b347  call    ?FreeBlbBackupSetArray@@YAXPEAPEAU_BLB_BACKUP_SET_INFO@@PEAK@Z; FreeBlbBackupSetArray(_BLB_BACKUP_SET_INFO * *,ulong *)
0x18008b34c  jmp     short loc_18008B359
0x18008b34e  mov     [rbp+var_40], 80070057h
0x18008b355  mov     [rbp+var_3A], ax
0x18008b359  mov     ebx, [rbp+var_40]
0x18008b35c  lea     rcx, [rbp+arg_8]
0x18008b360  call    ??1?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>(void)
0x18008b365  lea     rcx, [rbp+var_40]; this
0x18008b369  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008b36e  mov     eax, ebx
0x18008b370  mov     rbx, [rsp+80h+arg_18]
0x18008b378  add     rsp, 80h
0x18008b37f  pop     r15
0x18008b381  pop     r14
0x18008b383  pop     rdi
0x18008b384  pop     rsi
0x18008b385  pop     rbp
0x18008b386  retn
```
