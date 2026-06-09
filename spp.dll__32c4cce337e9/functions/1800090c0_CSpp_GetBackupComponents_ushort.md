# CSpp::GetBackupComponents(ushort * *)

- ea: `0x1800090c0`
- end: `0x1800091b5`
- name: `?GetBackupComponents@CSpp@@UEAAJPEAPEAG@Z`
- size: `245`
- prototype: `__int64 __fastcall(CSpp *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800090c0`
- `0x180017c74`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000918f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000918f`

## string_xrefs

- `0x18000910f`: `CSpp::GetBackupComponents`

## pseudocode

```c
__int64 __fastcall CSpp::GetBackupComponents(CSpp *this, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rcx
  __int16 v5; // ax
  struct IVssBackupComponents *v6; // rdx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  int BackupDocument; // [rsp+20h] [rbp-40h] BYREF
  __int16 v12; // [rsp+24h] [rbp-3Ch]
  __int16 v13; // [rsp+26h] [rbp-3Ah]
  unsigned __int16 *v14; // [rsp+78h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&BackupDocument, "CSpp::GetBackupComponents", 10390, 1);
  v4 = 0;
  v5 = 10396;
  v14 = 0;
  if ( !a2 )
  {
    BackupDocument = -2147024809;
    goto LABEL_11;
  }
  *a2 = 0;
  v6 = (struct IVssBackupComponents *)*((_QWORD *)this + 10);
  v12 = 10396;
  v5 = 10398;
  if ( !v6 )
  {
    BackupDocument = -2130706170;
LABEL_11:
    v13 = v5;
    goto LABEL_12;
  }
  BackupDocument = 0;
  v12 = 10398;
  BackupDocument = CSpp::_GetBackupDocument(0, v6, &v14);
  v5 = 10400;
  if ( BackupDocument < 0 )
  {
    v4 = v14;
    goto LABEL_11;
  }
  v12 = 10400;
  v4 = 0;
  *a2 = v14;
LABEL_12:
  CoTaskMemFree(v4);
  v7 = BackupDocument;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&BackupDocument, v8, v9);
  return v7;
}

```

## disassembly

```asm
0x1800090c0  mov     [rsp-8+arg_0], rbx
0x1800090c5  mov     [rsp-8+arg_10], rdi
0x1800090ca  push    rbp
0x1800090cb  mov     rbp, rsp
0x1800090ce  sub     rsp, 60h
0x1800090d2  mov     rbx, rdx
0x1800090d5  mov     rdi, rcx
0x1800090d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090df  lea     rax, WPP_GLOBAL_Control
0x1800090e6  cmp     rcx, rax
0x1800090e9  jz      short loc_180009109
0x1800090eb  test    dword ptr [rcx+1Ch], 20000000h
0x1800090f2  jz      short loc_180009109
0x1800090f4  mov     rcx, [rcx+10h]
0x1800090f8  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x1800090ff  mov     edx, 0B4h
0x180009104  call    WPP_SF_
0x180009109  mov     r9d, 1; unsigned __int16
0x18000910f  lea     rdx, aCsppGetbackupc; "CSpp::GetBackupComponents"
0x180009116  mov     r8d, 2896h; unsigned __int16
0x18000911c  lea     rcx, [rbp+var_40]; this
0x180009120  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180009125  xor     ecx, ecx; this
0x180009127  mov     eax, 289Ch
0x18000912c  mov     [rbp+arg_8], rcx
0x180009130  test    rbx, rbx
0x180009133  jz      short loc_180009184
0x180009135  mov     [rbx], rcx
0x180009138  mov     rdx, [rdi+50h]; struct IVssBackupComponents *
0x18000913c  mov     [rbp+var_3C], ax
0x180009140  mov     eax, 289Eh
0x180009145  test    rdx, rdx
0x180009148  jnz     short loc_180009153
0x18000914a  mov     [rbp+var_40], 81000106h
0x180009151  jmp     short loc_18000918B
0x180009153  lea     r8, [rbp+arg_8]; unsigned __int16 **
0x180009157  mov     [rbp+var_40], ecx
0x18000915a  mov     [rbp+var_3C], ax
0x18000915e  call    ?_GetBackupDocument@CSpp@@AEAAJPEAVIVssBackupComponents@@PEAPEAG@Z; CSpp::_GetBackupDocument(IVssBackupComponents *,ushort * *)
0x180009163  mov     [rbp+var_40], eax
0x180009166  test    eax, eax
0x180009168  mov     eax, 28A0h
0x18000916d  jns     short loc_180009175
0x18000916f  mov     rcx, [rbp+arg_8]
0x180009173  jmp     short loc_18000918B
0x180009175  mov     [rbp+var_3C], ax
0x180009179  xor     ecx, ecx
0x18000917b  mov     rax, [rbp+arg_8]
0x18000917f  mov     [rbx], rax
0x180009182  jmp     short loc_18000918F
0x180009184  mov     [rbp+var_40], 80070057h
0x18000918b  mov     [rbp+var_3A], ax
0x18000918f  call    cs:__imp_CoTaskMemFree
0x180009195  mov     ebx, [rbp+var_40]
0x180009198  lea     rcx, [rbp+var_40]; this
0x18000919c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800091a1  lea     r11, [rsp+60h+var_s0]
0x1800091a6  mov     eax, ebx
0x1800091a8  mov     rbx, [r11+10h]
0x1800091ac  mov     rdi, [r11+20h]
0x1800091b0  mov     rsp, r11
0x1800091b3  pop     rbp
0x1800091b4  retn
```
