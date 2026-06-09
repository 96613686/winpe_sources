# CSdController::_ConfigureEngine(ISdBackup2 *,ushort const *,_SD_BACKUP_CONFIG *,long *)

- ea: `0x1800115dc`
- end: `0x180011757`
- name: `?_ConfigureEngine@CSdController@@AEAAJPEAUISdBackup2@@PEBGPEAU_SD_BACKUP_CONFIG@@PEAJ@Z`
- size: `379`
- prototype: `__int64 __fastcall(CSdController *this, struct ISdBackup2 *, const unsigned __int16 *, struct _SD_BACKUP_CONFIG *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180012948`

## callees

- `0x1800106f4`
- `0x1800115dc`
- `0x18001586c`
- `0x180015974`
- `0x180022010`

## string_xrefs

- `0x180011600`: `CSdController::_ConfigureEngine`

## pseudocode

```c
__int64 __fastcall CSdController::_ConfigureEngine(
        CSdController *this,
        struct ISdBackup2 *a2,
        const unsigned __int16 *a3,
        struct _SD_BACKUP_CONFIG *a4,
        int *a5)
{
  __int16 v9; // ax
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // ebx
  __int64 v14; // rsi
  int v16; // [rsp+28h] [rbp-39h]
  int v17; // [rsp+40h] [rbp-21h] BYREF
  __int16 i; // [rsp+44h] [rbp-1Dh]
  __int16 v19; // [rsp+46h] [rbp-1Bh]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "CSdController::_ConfigureEngine", 0x236u, 0);
  v9 = 571;
  if ( !a2 || (i = 571, v9 = 572, !a3) || (i = 572, v9 = 573, !a4) || (i = 573, v9 = 574, !a5) )
  {
    v13 = -2147024809;
    v17 = -2147024809;
    goto LABEL_14;
  }
  v10 = *(_DWORD *)a4 | 8u;
  v16 = *((_DWORD *)a4 + 58);
  v11 = *((_QWORD *)a4 + 2);
  i = 574;
  v12 = *(_QWORD *)a2;
  v17 = 0;
  v13 = (*(__int64 (**)(struct ISdBackup2 *, const unsigned __int16 *, __int64, _QWORD, __int64, int, const wchar_t *, ...))(v12 + 24))(
          a2,
          a3,
          v10,
          0,
          v11,
          v16,
          L"%windir%\\Logs\\WindowsBackup");
  v17 = v13;
  v9 = 581;
  if ( v13 < 0 )
  {
LABEL_14:
    v19 = v9;
    goto LABEL_15;
  }
  v14 = 0;
  for ( i = 581; (unsigned int)v14 < *((_DWORD *)a4 + 6); i = 586 )
  {
    v13 = (*(__int64 (__fastcall **)(struct ISdBackup2 *, _QWORD, _QWORD))(*(_QWORD *)a2 + 32LL))(
            a2,
            *(_QWORD *)(*((_QWORD *)a4 + 4) + 24 * v14),
            *(unsigned int *)(*((_QWORD *)a4 + 4) + 24 * v14 + 16));
    v17 = v13;
    v9 = 586;
    if ( v13 < 0 )
      goto LABEL_14;
    v14 = (unsigned int)(v14 + 1);
  }
  if ( !*((_DWORD *)a4 + 60) || *((_DWORD *)a4 + 59) )
  {
    v13 = CSdController::_AddAllUsersDataPathsToEngine(this, a2, a4, a5);
    v17 = v13;
    v9 = 591;
    if ( v13 >= 0 )
    {
      i = 591;
      goto LABEL_15;
    }
    goto LABEL_14;
  }
LABEL_15:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800115dc  push    rbp
0x1800115de  push    rbx
0x1800115df  push    rsi
0x1800115e0  push    rdi
0x1800115e1  push    r12
0x1800115e3  push    r14
0x1800115e5  lea     rbp, [rsp-27h]
0x1800115ea  sub     rsp, 88h
0x1800115f1  mov     rdi, r9
0x1800115f4  mov     rbx, r8
0x1800115f7  mov     r14, rdx
0x1800115fa  mov     r12, rcx
0x1800115fd  xor     r9d, r9d; unsigned __int16
0x180011600  lea     rdx, aCsdcontrollerC_1; "CSdController::_ConfigureEngine"
0x180011607  mov     r8d, 236h; unsigned __int16
0x18001160d  lea     rcx, [rbp+4Fh+var_70]; this
0x180011611  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180011616  mov     eax, 23Bh
0x18001161b  test    r14, r14
0x18001161e  jz      loc_180011730
0x180011624  mov     [rbp+4Fh+var_6C], ax
0x180011628  mov     eax, 23Ch
0x18001162d  test    rbx, rbx
0x180011630  jz      loc_180011730
0x180011636  mov     [rbp+4Fh+var_6C], ax
0x18001163a  mov     eax, 23Dh
0x18001163f  test    rdi, rdi
0x180011642  jz      loc_180011730
0x180011648  cmp     [rbp+4Fh+arg_20], 0
0x18001164d  mov     [rbp+4Fh+var_6C], ax
0x180011651  mov     eax, 23Eh
0x180011656  jz      loc_180011730
0x18001165c  mov     r8d, [rdi]
0x18001165f  lea     rcx, aWindirLogsWind; "%windir%\\Logs\\WindowsBackup"
0x180011666  mov     [rsp+0B0h+var_80], rcx
0x18001166b  or      r8d, 8
0x18001166f  mov     ecx, [rdi+0E8h]
0x180011675  xor     r9d, r9d
0x180011678  mov     [rsp+0B0h+var_88], ecx
0x18001167c  mov     rdx, rbx
0x18001167f  mov     rcx, [rdi+10h]
0x180011683  mov     [rbp+4Fh+var_6C], ax
0x180011687  mov     rax, [r14]
0x18001168a  mov     [rsp+0B0h+var_90], rcx
0x18001168f  mov     rcx, r14
0x180011692  mov     [rbp+4Fh+var_70], 0
0x180011699  mov     rax, [rax+18h]
0x18001169d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116a2  mov     ebx, eax
0x1800116a4  mov     [rbp+4Fh+var_70], eax
0x1800116a7  test    eax, eax
0x1800116a9  mov     eax, 245h
0x1800116ae  js      loc_180011738
0x1800116b4  xor     esi, esi
0x1800116b6  mov     [rbp+4Fh+var_6C], ax
0x1800116ba  cmp     [rdi+18h], esi
0x1800116bd  jbe     short loc_1800116F8
0x1800116bf  mov     rdx, [rdi+20h]
0x1800116c3  lea     rcx, [rsi+rsi*2]
0x1800116c7  mov     rax, [r14]
0x1800116ca  mov     r8d, [rdx+rcx*8+10h]
0x1800116cf  mov     rdx, [rdx+rcx*8]
0x1800116d3  mov     rcx, r14
0x1800116d6  mov     rax, [rax+20h]
0x1800116da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116df  mov     ebx, eax
0x1800116e1  mov     [rbp+4Fh+var_70], eax
0x1800116e4  test    eax, eax
0x1800116e6  mov     eax, 24Ah
0x1800116eb  js      short loc_180011738
0x1800116ed  inc     esi
0x1800116ef  mov     [rbp+4Fh+var_6C], ax
0x1800116f3  cmp     esi, [rdi+18h]
0x1800116f6  jb      short loc_1800116BF
0x1800116f8  cmp     dword ptr [rdi+0F0h], 0
0x1800116ff  jz      short loc_18001170A
0x180011701  cmp     dword ptr [rdi+0ECh], 0
0x180011708  jz      short loc_18001173C
0x18001170a  mov     r9, [rbp+4Fh+arg_20]; int *
0x18001170e  mov     r8, rdi; struct _SD_BACKUP_CONFIG *
0x180011711  mov     rdx, r14; struct ISdBackup2 *
0x180011714  mov     rcx, r12; this
0x180011717  call    ?_AddAllUsersDataPathsToEngine@CSdController@@AEAAJPEAUISdBackup2@@PEAU_SD_BACKUP_CONFIG@@PEAJ@Z; CSdController::_AddAllUsersDataPathsToEngine(ISdBackup2 *,_SD_BACKUP_CONFIG *,long *)
0x18001171c  mov     ebx, eax
0x18001171e  mov     [rbp+4Fh+var_70], eax
0x180011721  test    eax, eax
0x180011723  mov     eax, 24Fh
0x180011728  js      short loc_180011738
0x18001172a  mov     [rbp+4Fh+var_6C], ax
0x18001172e  jmp     short loc_18001173C
0x180011730  mov     ebx, 80070057h
0x180011735  mov     [rbp+4Fh+var_70], ebx
0x180011738  mov     [rbp+4Fh+var_6A], ax
0x18001173c  lea     rcx, [rbp+4Fh+var_70]; this
0x180011740  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180011745  mov     eax, ebx
0x180011747  add     rsp, 88h
0x18001174e  pop     r14
0x180011750  pop     r12
0x180011752  pop     rdi
0x180011753  pop     rsi
0x180011754  pop     rbx
0x180011755  pop     rbp
0x180011756  retn
```
