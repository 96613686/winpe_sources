# _GetWinREDevPath(void *,void *,ushort *,ulong)

- ea: `0x140023098`
- end: `0x1400232a3`
- name: `?_GetWinREDevPath@@YAHPEAX0PEAGK@Z`
- size: `523`
- prototype: `__int64 __fastcall(void *, void *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400229e4`

## callees

- `0x140022ec8`
- `0x140023098`
- `0x14003b0c0`
- `0x1400d257c`
- `0x1400d8774`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140023288`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140023288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002316b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400231d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400231ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002316b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400231d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400231ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140023252`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140023252`

## string_xrefs

- `0x1400231f4`: `_GetPathFromBcdePath( hStore, pOsDevice, pwszDevicePath, cchDevicePath )`
- `0x1400230d5`: `_GetWinREDevPath`
- `0x14002326e`: `_GetWinREDevPath`
- `0x140023123`: `pwszDevicePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _GetWinREDevPath(void *a1, void *a2, unsigned __int16 *a3, unsigned int a4)
{
  struct _DRIVE_LAYOUT_INFORMATION_EX *v7; // rcx
  struct _BCDE_DEVICE *v8; // rbx
  unsigned int v9; // esi
  DWORD LastError; // edi
  int v11; // edx
  const char *v12; // rax
  DWORD v13; // eax
  DWORD v14; // r9d
  struct _BCDE_DEVICE *v16; // [rsp+60h] [rbp+18h] BYREF
  unsigned int v17; // [rsp+68h] [rbp+20h] BYREF

  v17 = a4;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x100000000LL) != 0 )
  {
    WPP_SF_S(
      *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
      10,
      WPP_1ff3ecedd42930a16d896984b72cfff5_Traceguids,
      L"_GetWinREDevPath");
    v7 = WPP_GLOBAL_Control;
  }
  v8 = 0;
  v17 = 0;
  v16 = 0;
  if ( a3 )
  {
    *a3 = 0;
    if ( (unsigned int)_GetElementData(a2, 0x21000001u, (void **)&v16, &v17) )
    {
      v8 = v16;
      if ( !v16 || ((*(_DWORD *)v16 - 2) & 0xFFFFFFFD) != 0 )
      {
        v9 = 0;
        LastError = 13;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
        {
          v11 = 54;
          v12 = "ERROR_INVALID_DATA";
          goto LABEL_23;
        }
      }
      else if ( (unsigned int)_GetPathFromBcdePath(a1, v16, a3, 0x104u) )
      {
        LastError = 0;
        v9 = 1;
      }
      else
      {
        v9 = 0;
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
        {
          v14 = GetLastError();
          WPP_SF_Ds(
            *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
            55,
            (unsigned int)WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids,
            v14,
            (__int64)"_GetPathFromBcdePath( hStore, pOsDevice, pwszDevicePath, cchDevicePath )");
        }
      }
    }
    else
    {
      v9 = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v13 = GetLastError();
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          53,
          (unsigned int)WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids,
          v13,
          (__int64)"_GetElementData( hObject, BCDE_OSLOADER_TYPE_OS_DEVICE, (PVOID*) &pOsDevice, &cbData )");
      }
      v8 = v16;
    }
  }
  else
  {
    v9 = 0;
    LastError = 87;
    if ( v7 != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (v7->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v11 = 52;
      v12 = "pwszDevicePath";
LABEL_23:
      WPP_SF_Ds(
        *(_QWORD *)v7->Gpt.DiskId.Data4,
        v11,
        (unsigned int)WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids,
        LastError,
        (__int64)v12);
    }
  }
  CoTaskMemFree(v8);
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x100000000LL) != 0 )
  {
    WPP_SF_S(
      *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
      11,
      WPP_1ff3ecedd42930a16d896984b72cfff5_Traceguids,
      L"_GetWinREDevPath");
  }
  SetLastError(LastError);
  return v9;
}

```

## disassembly

```asm
0x140023098  mov     [rsp+arg_0], rbx
0x14002309d  mov     [rsp+arg_8], rbp
0x1400230a2  mov     [rsp+arg_18], r9d
0x1400230a7  push    rsi
0x1400230a8  push    rdi
0x1400230a9  push    r14
0x1400230ab  sub     rsp, 30h
0x1400230af  mov     rdi, r8
0x1400230b2  mov     rsi, rdx
0x1400230b5  mov     rbp, rcx
0x1400230b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400230bf  lea     r14, WPP_GLOBAL_Control
0x1400230c6  cmp     rcx, r14
0x1400230c9  jz      short loc_1400230F4
0x1400230cb  test    byte ptr [rcx+1Ch], 1
0x1400230cf  jz      short loc_1400230F4
0x1400230d1  mov     rcx, [rcx+10h]
0x1400230d5  lea     r9, aGetwinredevpat; "_GetWinREDevPath"
0x1400230dc  mov     edx, 0Ah
0x1400230e1  lea     r8, WPP_1ff3ecedd42930a16d896984b72cfff5_Traceguids
0x1400230e8  call    WPP_SF_S
0x1400230ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400230f4  xor     ebx, ebx
0x1400230f6  mov     [rsp+48h+arg_18], 0
0x1400230fe  mov     [rsp+48h+arg_10], rbx
0x140023103  test    rdi, rdi
0x140023106  jnz     short loc_14002312F
0x140023108  xor     esi, esi
0x14002310a  lea     edi, [rbx+57h]
0x14002310d  cmp     rcx, r14
0x140023110  jz      loc_14002324F
0x140023116  test    byte ptr [rcx+1Ch], 8
0x14002311a  jz      loc_14002324F
0x140023120  lea     edx, [rbx+34h]
0x140023123  lea     rax, aPwszdevicepath; "pwszDevicePath"
0x14002312a  jmp     loc_140023237
0x14002312f  xor     eax, eax
0x140023131  lea     r9, [rsp+48h+arg_18]; unsigned int *
0x140023136  lea     r8, [rsp+48h+arg_10]; void **
0x14002313b  mov     [rdi], ax
0x14002313e  mov     edx, 21000001h; unsigned int
0x140023143  mov     rcx, rsi; void *
0x140023146  call    ?_GetElementData@@YAHPEAXKPEAPEAXPEAK@Z; _GetElementData(void *,ulong,void * *,ulong *)
0x14002314b  test    eax, eax
0x14002314d  jnz     short loc_1400231A4
0x14002314f  xor     esi, esi
0x140023151  call    cs:__imp_GetLastError
0x140023157  mov     edi, eax
0x140023159  mov     rax, cs:WPP_GLOBAL_Control
0x140023160  cmp     rax, r14
0x140023163  jz      short loc_14002319A
0x140023165  test    byte ptr [rax+1Ch], 8
0x140023169  jz      short loc_14002319A
0x14002316b  call    cs:__imp_GetLastError
0x140023171  lea     rcx, aGetelementdata; "_GetElementData( hObject, BCDE_OSLOADER"...
0x140023178  mov     r9d, eax
0x14002317b  mov     [rsp+48h+var_28], rcx
0x140023180  lea     edx, [rsi+35h]
0x140023183  mov     rcx, cs:WPP_GLOBAL_Control
0x14002318a  lea     r8, WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids
0x140023191  mov     rcx, [rcx+10h]
0x140023195  call    WPP_SF_Ds
0x14002319a  mov     rbx, [rsp+48h+arg_10]
0x14002319f  jmp     loc_14002324F
0x1400231a4  mov     rbx, [rsp+48h+arg_10]
0x1400231a9  test    rbx, rbx
0x1400231ac  jz      short loc_140023216
0x1400231ae  mov     eax, [rbx]
0x1400231b0  sub     eax, 2
0x1400231b3  test    eax, 0FFFFFFFDh
0x1400231b8  jnz     short loc_140023216
0x1400231ba  mov     r9d, 104h; unsigned int
0x1400231c0  mov     r8, rdi; unsigned __int16 *
0x1400231c3  mov     rdx, rbx; struct _BCDE_DEVICE *
0x1400231c6  mov     rcx, rbp; void *
0x1400231c9  call    ?_GetPathFromBcdePath@@YAHPEAXPEBU_BCDE_DEVICE@@PEAGK@Z; _GetPathFromBcdePath(void *,_BCDE_DEVICE const *,ushort *,ulong)
0x1400231ce  test    eax, eax
0x1400231d0  jnz     short loc_14002320F
0x1400231d2  xor     esi, esi
0x1400231d4  call    cs:__imp_GetLastError
0x1400231da  mov     edi, eax
0x1400231dc  mov     rax, cs:WPP_GLOBAL_Control
0x1400231e3  cmp     rax, r14
0x1400231e6  jz      short loc_14002324F
0x1400231e8  test    byte ptr [rax+1Ch], 8
0x1400231ec  jz      short loc_14002324F
0x1400231ee  call    cs:__imp_GetLastError
0x1400231f4  lea     rcx, aGetpathfrombcd_2; "_GetPathFromBcdePath( hStore, pOsDevice"...
0x1400231fb  mov     r9d, eax
0x1400231fe  mov     [rsp+48h+var_28], rcx
0x140023203  lea     edx, [rsi+37h]
0x140023206  mov     rcx, cs:WPP_GLOBAL_Control
0x14002320d  jmp     short loc_14002323F
0x14002320f  xor     edi, edi
0x140023211  lea     esi, [rdi+1]
0x140023214  jmp     short loc_14002324F
0x140023216  xor     esi, esi
0x140023218  lea     edi, [rsi+0Dh]
0x14002321b  mov     rcx, cs:WPP_GLOBAL_Control
0x140023222  cmp     rcx, r14
0x140023225  jz      short loc_14002324F
0x140023227  test    byte ptr [rcx+1Ch], 8
0x14002322b  jz      short loc_14002324F
0x14002322d  lea     edx, [rsi+36h]
0x140023230  lea     rax, aErrorInvalidDa; "ERROR_INVALID_DATA"
0x140023237  mov     [rsp+48h+var_28], rax
0x14002323c  mov     r9d, edi
0x14002323f  mov     rcx, [rcx+10h]
0x140023243  lea     r8, WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids
0x14002324a  call    WPP_SF_Ds
0x14002324f  mov     rcx, rbx; pv
0x140023252  call    cs:__imp_CoTaskMemFree
0x140023258  mov     rcx, cs:WPP_GLOBAL_Control
0x14002325f  cmp     rcx, r14
0x140023262  jz      short loc_140023286
0x140023264  test    byte ptr [rcx+1Ch], 1
0x140023268  jz      short loc_140023286
0x14002326a  mov     rcx, [rcx+10h]
0x14002326e  lea     r9, aGetwinredevpat; "_GetWinREDevPath"
0x140023275  mov     edx, 0Bh
0x14002327a  lea     r8, WPP_1ff3ecedd42930a16d896984b72cfff5_Traceguids
0x140023281  call    WPP_SF_S
0x140023286  mov     ecx, edi; dwErrCode
0x140023288  call    cs:__imp_SetLastError
0x14002328e  mov     rbx, [rsp+48h+arg_0]
0x140023293  mov     eax, esi
0x140023295  mov     rbp, [rsp+48h+arg_8]
0x14002329a  add     rsp, 30h
0x14002329e  pop     r14
0x1400232a0  pop     rdi
0x1400232a1  pop     rsi
0x1400232a2  retn
```
