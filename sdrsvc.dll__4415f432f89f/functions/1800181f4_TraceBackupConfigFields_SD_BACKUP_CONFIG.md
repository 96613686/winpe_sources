# TraceBackupConfigFields(_SD_BACKUP_CONFIG *)

- ea: `0x1800181f4`
- end: `0x180018483`
- name: `?TraceBackupConfigFields@@YAJPEAU_SD_BACKUP_CONFIG@@@Z`
- size: `655`
- prototype: `__int64 __fastcall(struct _SD_BACKUP_CONFIG *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180012948`

## callees

- `0x18000ea0c`
- `0x18000ea7c`
- `0x180014f70`
- `0x18001586c`
- `0x180015974`
- `0x1800172ec`
- `0x1800181f4`
- `0x18001848c`
- `0x180018654`
- `0x18001892c`

## string_xrefs

- `0x180018208`: `TraceBackupConfigFields`

## pseudocode

```c
__int64 __fastcall TraceBackupConfigFields(struct _SD_BACKUP_CONFIG *a1)
{
  __int64 v2; // r8
  _QWORD *v3; // rcx
  __int64 v4; // r14
  unsigned int v5; // esi
  _UNKNOWN **v6; // r10
  __int64 v7; // rdi
  unsigned int v8; // ebx
  int v10; // [rsp+40h] [rbp-A8h] BYREF
  __int16 v11; // [rsp+44h] [rbp-A4h]
  _DWORD v12[28]; // [rsp+78h] [rbp-70h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v12, "TraceBackupConfigFields", 154, 1);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_f3432682207f31e848c52635aa09a2d5_Traceguids,
        *((_QWORD *)a1 + 1));
      v3 = WPP_GLOBAL_Control;
    }
    if ( v3 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v3 + 28) & 0x40) != 0 )
      {
        WPP_SF_S(v3[2], 11, &WPP_f3432682207f31e848c52635aa09a2d5_Traceguids, *((_QWORD *)a1 + 2));
        v3 = WPP_GLOBAL_Control;
      }
      if ( v3 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v3 + 28) & 0x40) != 0 )
        {
          WPP_SF_D(v3[2], 12, v2, *(unsigned int *)a1);
          v3 = WPP_GLOBAL_Control;
        }
        if ( v3 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v3 + 28) & 0x40) != 0 )
          {
            WPP_SF_d(v3[2], 13, &WPP_f3432682207f31e848c52635aa09a2d5_Traceguids, *((unsigned int *)a1 + 59));
            v3 = WPP_GLOBAL_Control;
          }
          if ( v3 != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v3 + 28) & 0x40) != 0 )
            {
              WPP_SF_S(v3[2], 14, &WPP_f3432682207f31e848c52635aa09a2d5_Traceguids, *((_QWORD *)a1 + 27));
              v3 = WPP_GLOBAL_Control;
            }
            if ( v3 != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v3 + 28) & 0x40) != 0 )
              {
                WPP_SF_S(v3[2], 15, &WPP_f3432682207f31e848c52635aa09a2d5_Traceguids, *((_QWORD *)a1 + 28));
                v3 = WPP_GLOBAL_Control;
              }
              if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x40) != 0 )
                WPP_SF_S(v3[2], 16, &WPP_f3432682207f31e848c52635aa09a2d5_Traceguids, *((_QWORD *)a1 + 25));
            }
          }
        }
      }
    }
  }
  TraceStorageDeviceProp((struct _SD_BACKUP_CONFIG *)((char *)a1 + 40));
  v4 = *((_QWORD *)a1 + 4);
  v5 = *((_DWORD *)a1 + 6);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "TraceBackupRoots", 206, 1);
  v6 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_f3432682207f31e848c52635aa09a2d5_Traceguids);
    v6 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( v5 && v4 )
  {
    v7 = 0;
    do
    {
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 )
      {
        WPP_SF_dSSD(
          (TRACEHANDLE)v6[2],
          *(_QWORD *)(v4 + 24 * v7),
          *(_QWORD *)(v4 + 24 * v7 + 8),
          *(_DWORD *)(v4 + 24 * v7 + 16));
        v6 = (_UNKNOWN **)WPP_GLOBAL_Control;
      }
      v7 = (unsigned int)(v7 + 1);
    }
    while ( (unsigned int)v7 < v5 );
  }
  else
  {
    v10 = 0;
    v11 = 215;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      &WPP_f3432682207f31e848c52635aa09a2d5_Traceguids,
      *((unsigned int *)a1 + 60));
  TraceBackupUsers(*((_DWORD *)a1 + 48), *((struct _SD_BACKUP_USER_DATA **)a1 + 23));
  v8 = v12[0];
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v12);
  return v8;
}

```

## disassembly

```asm
0x1800181f4  push    rbx
0x1800181f6  push    rsi
0x1800181f7  push    rdi
0x1800181f8  push    r12
0x1800181fa  push    r14
0x1800181fc  push    r15
0x1800181fe  sub     rsp, 0B8h
0x180018205  mov     rbx, rcx
0x180018208  lea     rdx, aTracebackupcon; "TraceBackupConfigFields"
0x18001820f  lea     rcx, [rsp+0E8h+var_70]; this
0x180018214  mov     r9d, 1; unsigned __int16
0x18001821a  mov     r8d, 9Ah; unsigned __int16
0x180018220  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180018225  mov     rcx, cs:WPP_GLOBAL_Control
0x18001822c  lea     r15, WPP_GLOBAL_Control
0x180018233  lea     r12, WPP_f3432682207f31e848c52635aa09a2d5_Traceguids
0x18001823a  cmp     rcx, r15
0x18001823d  jz      loc_18001835C
0x180018243  test    byte ptr [rcx+1Ch], 40h
0x180018247  jz      short loc_180018265
0x180018249  mov     r9, [rbx+8]
0x18001824d  mov     edx, 0Ah
0x180018252  mov     rcx, [rcx+10h]
0x180018256  mov     r8, r12
0x180018259  call    WPP_SF_S
0x18001825e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018265  cmp     rcx, r15
0x180018268  jz      loc_18001835C
0x18001826e  test    byte ptr [rcx+1Ch], 40h
0x180018272  jz      short loc_180018290
0x180018274  mov     r9, [rbx+10h]
0x180018278  mov     edx, 0Bh
0x18001827d  mov     rcx, [rcx+10h]
0x180018281  mov     r8, r12
0x180018284  call    WPP_SF_S
0x180018289  mov     rcx, cs:WPP_GLOBAL_Control
0x180018290  cmp     rcx, r15
0x180018293  jz      loc_18001835C
0x180018299  test    byte ptr [rcx+1Ch], 40h
0x18001829d  jz      short loc_1800182B7
0x18001829f  mov     r9d, [rbx]
0x1800182a2  mov     edx, 0Ch
0x1800182a7  mov     rcx, [rcx+10h]
0x1800182ab  call    WPP_SF_D
0x1800182b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182b7  cmp     rcx, r15
0x1800182ba  jz      loc_18001835C
0x1800182c0  test    byte ptr [rcx+1Ch], 40h
0x1800182c4  jz      short loc_1800182E5
0x1800182c6  mov     r9d, [rbx+0ECh]
0x1800182cd  mov     edx, 0Dh
0x1800182d2  mov     rcx, [rcx+10h]
0x1800182d6  mov     r8, r12
0x1800182d9  call    WPP_SF_d
0x1800182de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182e5  cmp     rcx, r15
0x1800182e8  jz      short loc_18001835C
0x1800182ea  test    byte ptr [rcx+1Ch], 40h
0x1800182ee  jz      short loc_18001830F
0x1800182f0  mov     r9, [rbx+0D8h]
0x1800182f7  mov     edx, 0Eh
0x1800182fc  mov     rcx, [rcx+10h]
0x180018300  mov     r8, r12
0x180018303  call    WPP_SF_S
0x180018308  mov     rcx, cs:WPP_GLOBAL_Control
0x18001830f  cmp     rcx, r15
0x180018312  jz      short loc_18001835C
0x180018314  test    byte ptr [rcx+1Ch], 40h
0x180018318  jz      short loc_180018339
0x18001831a  mov     r9, [rbx+0E0h]
0x180018321  mov     edx, 0Fh
0x180018326  mov     rcx, [rcx+10h]
0x18001832a  mov     r8, r12
0x18001832d  call    WPP_SF_S
0x180018332  mov     rcx, cs:WPP_GLOBAL_Control
0x180018339  cmp     rcx, r15
0x18001833c  jz      short loc_18001835C
0x18001833e  test    byte ptr [rcx+1Ch], 40h
0x180018342  jz      short loc_18001835C
0x180018344  mov     r9, [rbx+0C8h]
0x18001834b  mov     edx, 10h
0x180018350  mov     rcx, [rcx+10h]
0x180018354  mov     r8, r12
0x180018357  call    WPP_SF_S
0x18001835c  lea     rcx, [rbx+28h]; struct _SD_STORAGE_DEVICE_PROP *
0x180018360  call    ?TraceStorageDeviceProp@@YAJPEAU_SD_STORAGE_DEVICE_PROP@@@Z; TraceStorageDeviceProp(_SD_STORAGE_DEVICE_PROP *)
0x180018365  mov     r14, [rbx+20h]
0x180018369  lea     rdx, aTracebackuproo; "TraceBackupRoots"
0x180018370  mov     esi, [rbx+18h]
0x180018373  lea     rcx, [rsp+0E8h+var_A8]; this
0x180018378  mov     r9d, 1; unsigned __int16
0x18001837e  mov     r8d, 0CEh; unsigned __int16
0x180018384  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180018389  mov     r10, cs:WPP_GLOBAL_Control
0x180018390  cmp     r10, r15
0x180018393  jz      short loc_1800183B4
0x180018395  test    byte ptr [r10+1Ch], 40h
0x18001839a  jz      short loc_1800183B4
0x18001839c  mov     rcx, [r10+10h]
0x1800183a0  mov     edx, 1Dh
0x1800183a5  mov     r8, r12
0x1800183a8  call    WPP_SF_
0x1800183ad  mov     r10, cs:WPP_GLOBAL_Control
0x1800183b4  test    esi, esi
0x1800183b6  jz      short loc_18001840A
0x1800183b8  test    r14, r14
0x1800183bb  jz      short loc_18001840A
0x1800183bd  xor     edi, edi
0x1800183bf  test    esi, esi
0x1800183c1  jz      short loc_18001841C
0x1800183c3  cmp     r10, r15
0x1800183c6  jz      short loc_180018402
0x1800183c8  test    byte ptr [r10+1Ch], 40h
0x1800183cd  jz      short loc_180018402
0x1800183cf  lea     rcx, [rdi+rdi*2]
0x1800183d3  mov     r9d, edi
0x1800183d6  mov     eax, [r14+rcx*8+10h]
0x1800183db  mov     dword ptr [rsp+0E8h+var_B8], eax; char
0x1800183df  mov     rax, [r14+rcx*8+8]
0x1800183e4  mov     [rsp+0E8h+var_C0], rax; __int64
0x1800183e9  mov     rax, [r14+rcx*8]
0x1800183ed  mov     rcx, [r10+10h]; LoggerHandle
0x1800183f1  mov     [rsp+0E8h+var_C8], rax; __int64
0x1800183f6  call    WPP_SF_dSSD
0x1800183fb  mov     r10, cs:WPP_GLOBAL_Control
0x180018402  inc     edi
0x180018404  cmp     edi, esi
0x180018406  jb      short loc_1800183C3
0x180018408  jmp     short loc_18001841C
0x18001840a  mov     eax, 0D7h
0x18001840f  mov     [rsp+0E8h+var_A8], 0
0x180018417  mov     [rsp+0E8h+var_A4], ax
0x18001841c  lea     rcx, [rsp+0E8h+var_A8]; this
0x180018421  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180018426  mov     rcx, cs:WPP_GLOBAL_Control
0x18001842d  cmp     rcx, r15
0x180018430  jz      short loc_180018450
0x180018432  test    byte ptr [rcx+1Ch], 40h
0x180018436  jz      short loc_180018450
0x180018438  mov     r9d, [rbx+0F0h]
0x18001843f  mov     edx, 11h
0x180018444  mov     rcx, [rcx+10h]
0x180018448  mov     r8, r12
0x18001844b  call    WPP_SF_d
0x180018450  mov     rdx, [rbx+0B8h]; struct _SD_BACKUP_USER_DATA *
0x180018457  mov     ecx, [rbx+0C0h]; unsigned int
0x18001845d  call    ?TraceBackupUsers@@YAJKPEAU_SD_BACKUP_USER_DATA@@@Z; TraceBackupUsers(ulong,_SD_BACKUP_USER_DATA *)
0x180018462  mov     ebx, [rsp+0E8h+var_70]
0x180018466  lea     rcx, [rsp+0E8h+var_70]; this
0x18001846b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180018470  mov     eax, ebx
0x180018472  add     rsp, 0B8h
0x180018479  pop     r15
0x18001847b  pop     r14
0x18001847d  pop     r12
0x18001847f  pop     rdi
0x180018480  pop     rsi
0x180018481  pop     rbx
0x180018482  retn
```
