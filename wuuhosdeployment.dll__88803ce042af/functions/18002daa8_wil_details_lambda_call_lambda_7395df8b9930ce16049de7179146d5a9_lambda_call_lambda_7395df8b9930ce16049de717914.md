# wil::details::lambda_call__lambda_7395df8b9930ce16049de7179146d5a9___::_lambda_call__lambda_7395df8b9930ce16049de7179146d5a9___

- ea: `0x18002daa8`
- end: `0x18002db71`
- name: `wil::details::lambda_call__lambda_7395df8b9930ce16049de7179146d5a9___::_lambda_call__lambda_7395df8b9930ce16049de7179146d5a9___`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800276d0`
- `0x18004a8ce`

## callees

- `0x18000956c`
- `0x18002b4fc`
- `0x18002daa8`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18002dae9`
- `OLEAUT32!__imp_SysStringLen` at `0x18002dae9`

## string_xrefs

- `0x18002db3b`: `Leave deployment handler Install`
- `0x18002db07`: `Error deleting merged update folder %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::lambda_call__lambda_7395df8b9930ce16049de7179146d5a9___::_lambda_call__lambda_7395df8b9930ce16049de7179146d5a9___(
        __int64 a1)
{
  _DWORD *v1; // rax
  wchar_t *const *v2; // rdi
  __int64 v3; // rsi
  COSInstaller *v4; // rcx

  if ( *(_BYTE *)(a1 + 40) )
  {
    *(_BYTE *)(a1 + 40) = 0;
    if ( **(_BYTE **)a1 )
    {
      v1 = *(_DWORD **)(a1 + 16);
      if ( *v1 )
      {
        v2 = (wchar_t *const *)(**(_QWORD **)(a1 + 24) + 24LL);
        v3 = (unsigned int)*v1;
        do
        {
          if ( SysStringLen(*v2) )
          {
            if ( (int)COSInstaller::DeleteMergedSandboxDir(v4, *v2) < 0 )
              WUTrace(0, 0, 4096, 3);
          }
          v2 += 37;
          --v3;
        }
        while ( v3 );
      }
    }
    WUTrace(0, 0, 4096, 4);
  }
}

```

## disassembly

```asm
0x18002daa8  mov     [rsp+arg_0], rbx
0x18002daad  mov     [rsp+arg_8], rsi
0x18002dab2  push    rdi
0x18002dab3  sub     rsp, 40h
0x18002dab7  mov     rbx, rcx
0x18002daba  cmp     byte ptr [rcx+28h], 0
0x18002dabe  jz      loc_18002DB61
0x18002dac4  mov     byte ptr [rcx+28h], 0
0x18002dac8  mov     rax, [rcx]
0x18002dacb  cmp     byte ptr [rax], 0
0x18002dace  jz      short loc_18002DB37
0x18002dad0  mov     rax, [rcx+18h]
0x18002dad4  mov     rdi, [rax]
0x18002dad7  mov     rax, [rcx+10h]
0x18002dadb  cmp     dword ptr [rax], 0
0x18002dade  jbe     short loc_18002DB37
0x18002dae0  add     rdi, 18h
0x18002dae4  mov     esi, [rax]
0x18002dae6  mov     rcx, [rdi]; pbstr
0x18002dae9  call    cs:__imp_SysStringLen
0x18002daef  test    eax, eax
0x18002daf1  jz      short loc_18002DB2A
0x18002daf3  mov     rdx, [rdi]; wchar_t *
0x18002daf6  call    ?DeleteMergedSandboxDir@COSInstaller@@AEAAJQEA_W@Z; COSInstaller::DeleteMergedSandboxDir(wchar_t * const)
0x18002dafb  test    eax, eax
0x18002dafd  jns     short loc_18002DB2A
0x18002daff  mov     rcx, [rdi]
0x18002db02  mov     [rsp+48h+var_18], rcx
0x18002db07  lea     rcx, aErrorDeletingM; "Error deleting merged update folder %ws"
0x18002db0e  mov     [rsp+48h+var_20], rcx
0x18002db13  mov     [rsp+48h+var_28], eax
0x18002db17  xor     edx, edx
0x18002db19  xor     ecx, ecx
0x18002db1b  lea     r9d, [rdx+3]
0x18002db1f  mov     r8d, 1000h
0x18002db25  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002db2a  add     rdi, 128h
0x18002db31  sub     rsi, 1
0x18002db35  jnz     short loc_18002DAE6
0x18002db37  mov     rax, [rbx+20h]
0x18002db3b  lea     rcx, aLeaveDeploymen_1; "Leave deployment handler Install"
0x18002db42  mov     [rsp+48h+var_20], rcx
0x18002db47  mov     eax, [rax]
0x18002db49  mov     [rsp+48h+var_28], eax
0x18002db4d  xor     edx, edx
0x18002db4f  xor     ecx, ecx
0x18002db51  lea     r9d, [rdx+4]
0x18002db55  mov     r8d, 1000h
0x18002db5b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002db60  nop
0x18002db61  mov     rbx, [rsp+48h+arg_0]
0x18002db66  mov     rsi, [rsp+48h+arg_8]
0x18002db6b  add     rsp, 40h
0x18002db6f  pop     rdi
0x18002db70  retn
```
