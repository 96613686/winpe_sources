# CSdController::_HasASRHappened(_SD_BACKUP_CONFIG const *)

- ea: `0x1800120dc`
- end: `0x1800121b5`
- name: `?_HasASRHappened@CSdController@@AEAAJPEBU_SD_BACKUP_CONFIG@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(CSdController *__hidden this, const struct _SD_BACKUP_CONFIG *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180012948`

## callees

- `0x1800120dc`
- `0x18001586c`
- `0x180015974`
- `0x18001e41c`
- `0x180020488`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180012166`
- `msvcrt!_wcsicmp` at `0x180012166`

## pseudocode

```c
__int64 __fastcall CSdController::_HasASRHappened(CSdController *this, const struct _SD_BACKUP_CONFIG *a2)
{
  __int16 v3; // ax
  int LastAsrRestoreId; // ebx
  const wchar_t *v5; // rdx
  __int16 v6; // ax
  wchar_t *String1[2]; // [rsp+20h] [rbp-50h] BYREF
  int v9; // [rsp+30h] [rbp-40h] BYREF
  __int16 v10; // [rsp+34h] [rbp-3Ch]
  __int16 v11; // [rsp+36h] [rbp-3Ah]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "CSdController::_HasASRHappened", 3288, 0);
  String1[1] = 0;
  String1[0] = (wchar_t *)qword_180028260;
  v3 = 3294;
  if ( !a2 )
  {
    LastAsrRestoreId = -2147024809;
    v9 = -2147024809;
LABEL_3:
    v11 = v3;
    goto LABEL_9;
  }
  v9 = 0;
  v10 = 3294;
  LastAsrRestoreId = SxGetLastAsrRestoreId((struct CBsString *)String1);
  v9 = LastAsrRestoreId;
  v3 = 3296;
  if ( LastAsrRestoreId < 0 )
    goto LABEL_3;
  v5 = (const wchar_t *)*((_QWORD *)a2 + 28);
  v10 = 3296;
  if ( _wcsicmp(String1[0], v5) )
  {
    v9 = 0;
    v6 = 3306;
    LastAsrRestoreId = 0;
  }
  else
  {
    LastAsrRestoreId = 1;
    v6 = 3301;
    v9 = 1;
  }
  v10 = v6;
LABEL_9:
  CBsString::_Release((CBsString *)String1);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return (unsigned int)LastAsrRestoreId;
}

```

## disassembly

```asm
0x1800120dc  mov     [rsp-8+arg_0], rbx
0x1800120e1  mov     [rsp-8+arg_8], rdi
0x1800120e6  push    rbp
0x1800120e7  mov     rbp, rsp
0x1800120ea  sub     rsp, 70h
0x1800120ee  mov     rdi, rdx
0x1800120f1  lea     rcx, [rbp+var_40]; this
0x1800120f5  lea     rdx, aCsdcontrollerH; "CSdController::_HasASRHappened"
0x1800120fc  xor     r9d, r9d; unsigned __int16
0x1800120ff  mov     r8d, 0CD8h; unsigned __int16
0x180012105  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001210a  mov     [rbp+var_48], 0
0x180012112  lea     rax, qword_180028260
0x180012119  mov     [rbp+String1], rax
0x18001211d  mov     eax, 0CDEh
0x180012122  test    rdi, rdi
0x180012125  jnz     short loc_180012135
0x180012127  mov     ebx, 80070057h
0x18001212c  mov     [rbp+var_40], ebx
0x18001212f  mov     [rbp+var_3A], ax
0x180012133  jmp     short loc_18001218F
0x180012135  lea     rcx, [rbp+String1]; this
0x180012139  mov     [rbp+var_40], 0
0x180012140  mov     [rbp+var_3C], ax
0x180012144  call    ?SxGetLastAsrRestoreId@@YAJPEAVCBsString@@@Z; SxGetLastAsrRestoreId(CBsString *)
0x180012149  mov     ebx, eax
0x18001214b  mov     [rbp+var_40], eax
0x18001214e  test    eax, eax
0x180012150  mov     eax, 0CE0h
0x180012155  js      short loc_18001212F
0x180012157  mov     rdx, [rdi+0E0h]; String2
0x18001215e  mov     rcx, [rbp+String1]; String1
0x180012162  mov     [rbp+var_3C], ax
0x180012166  call    cs:__imp__wcsicmp
0x18001216c  test    eax, eax
0x18001216e  jnz     short loc_18001217D
0x180012170  lea     ebx, [rax+1]
0x180012173  mov     eax, 0CE5h
0x180012178  mov     [rbp+var_40], ebx
0x18001217b  jmp     short loc_18001218B
0x18001217d  mov     [rbp+var_40], 0
0x180012184  mov     eax, 0CEAh
0x180012189  xor     ebx, ebx
0x18001218b  mov     [rbp+var_3C], ax
0x18001218f  lea     rcx, [rbp+String1]; this
0x180012193  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180012198  lea     rcx, [rbp+var_40]; this
0x18001219c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800121a1  lea     r11, [rsp+70h+var_s0]
0x1800121a6  mov     eax, ebx
0x1800121a8  mov     rbx, [r11+10h]
0x1800121ac  mov     rdi, [r11+18h]
0x1800121b0  mov     rsp, r11
0x1800121b3  pop     rbp
0x1800121b4  retn
```
