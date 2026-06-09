# WiaTrace_Trace

- ea: `0x18000da10`
- end: `0x18000dcf9`
- name: `WiaTrace_Trace`
- size: `745`
- prototype: `__int64(const char *, ...)`
- caller_count: `503`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180001cd4`
- `0x180002610`
- `0x1800028f4`
- `0x180002c24`
- `0x180003080`
- `0x1800030f0`
- `0x1800033f4`
- `0x18000426c`
- `0x1800045e0`
- `0x18000469c`
- `0x180004790`
- `0x180004dbc`
- `0x180005a48`
- `0x180005e48`
- `0x180006300`
- `0x180006a2c`
- `0x180006f9c`
- `0x1800070fc`
- `0x180007324`
- `0x180007878`
- `0x1800085b0`
- `0x180008cac`
- `0x180009040`
- `0x18000a200`
- `0x18000a6b4`
- `0x18000a83c`
- `0x18000ac58`
- `0x18000bc50`
- `0x18000c040`
- `0x18000c7c0`
- `0x18000ce90`
- `0x18000de60`
- `0x18000e810`
- `0x18000ecf0`
- `0x18000f668`
- `0x18000f808`
- `0x18000fa20`
- `0x18000fa9c`
- `0x18000fbec`
- `0x18000fdf4`
- `0x180010730`
- `0x180010f0c`
- `0x180011c20`
- `0x180013944`
- `0x180013c80`
- `0x180014b9c`
- `0x180015aa0`
- `0x180015f90`
- `0x18001699c`
- `0x18001750c`

## callees

- `0x18000da10`
- `0x180033cc0`
- `0x180034658`
- `0x180034708`
- `0x180039b9c`
- `0x180078010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000dbfc`
- `KERNEL32!HeapFree` at `0x18000dbfc`
- `KERNEL32!GetProcessHeap` at `0x18000da55`
- `KERNEL32!GetProcessHeap` at `0x18000db6c`
- `KERNEL32!GetProcessHeap` at `0x18000dbee`
- `KERNEL32!GetProcessHeap` at `0x18000da55`
- `KERNEL32!GetProcessHeap` at `0x18000db6c`
- `KERNEL32!GetProcessHeap` at `0x18000dbee`
- `KERNEL32!GetCurrentProcessId` at `0x18000dad4`
- `KERNEL32!GetCurrentProcessId` at `0x18000dad4`
- `KERNEL32!GetCurrentThreadId` at `0x18000dadd`
- `KERNEL32!GetCurrentThreadId` at `0x18000dadd`
- `KERNEL32!HeapAlloc` at `0x18000da69`
- `KERNEL32!HeapAlloc` at `0x18000db7d`
- `KERNEL32!HeapAlloc` at `0x18000da69`
- `KERNEL32!HeapAlloc` at `0x18000db7d`

## pseudocode

```c
_DWORD *WiaTrace_Trace(const char *a1, ...)
{
  _DWORD *result; // rax
  HANDLE ProcessHeap; // rax
  _DWORD *v3; // rdi
  DWORD CurrentThreadId; // eax
  __int64 (*v5)(void); // rcx
  int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rax
  char *v9; // rsi
  unsigned __int64 v10; // rbx
  HANDLE v11; // rax
  char *v12; // rax
  char *v13; // rbp
  __int64 v14; // r8
  unsigned __int64 v15; // rcx
  char *v16; // rax
  unsigned __int64 v17; // r9
  int v18; // eax
  char *v19; // rax
  HANDLE v20; // rax
  char *v21; // rdx
  char *v22; // rcx
  unsigned __int64 i; // rbx
  int v24; // [rsp+20h] [rbp-248h] BYREF
  unsigned int v25; // [rsp+24h] [rbp-244h] BYREF
  __int64 v26; // [rsp+28h] [rbp-240h] BYREF
  char Buffer[512]; // [rsp+30h] [rbp-238h] BYREF
  va_list ArgList; // [rsp+278h] [rbp+10h] BYREF

  va_start(ArgList, a1);
  result = 0;
  if ( (g_WiaTrace_ulFlags & 1) != 0 )
  {
    ProcessHeap = GetProcessHeap();
    result = HeapAlloc(ProcessHeap, 8u, 0x40u);
    v3 = result;
    if ( result )
    {
      memset_0(Buffer, 0, sizeof(Buffer));
      memset_0(v3, 0, 0x40u);
      v26 = 0;
      if ( (unsigned int)vsnprintf(Buffer, 0x1FFu, a1, ArgList) > 0x1FE )
        Buffer[511] = 0;
      v3[3] = GetCurrentProcessId();
      CurrentThreadId = GetCurrentThreadId();
      v5 = (__int64 (*)(void))WiaTrcLib::g_WiaTrc_GetIndentLevel;
      v3[4] = CurrentThreadId;
      v6 = 0;
      if ( v5 )
        v6 = v5();
      v3[14] = v6;
      if ( WiaTrcLib::g_WiaTrc_GetTraceSettings )
      {
        v25 = 0;
        LODWORD(v26) = 0;
        v24 = 0;
        WiaTrcLib::g_WiaTrc_GetTraceSettings(&v25, (unsigned int *)&v26, &v24);
        if ( v24 )
        {
          v3[13] = v25;
          v3[15] = v26;
        }
        else
        {
          v3[13] = 0;
          v3[15] = 0;
        }
      }
      v7 = -1;
      v8 = -1;
      do
        ++v8;
      while ( Buffer[v8] );
      if ( v8 )
      {
        v9 = *(char **)v3;
        if ( *(_QWORD *)v3 )
        {
          do
            ++v7;
          while ( v9[v7] );
        }
        else
        {
          v9 = 0;
          LODWORD(v7) = 0;
        }
        if ( (_DWORD)v8 + (_DWORD)v7 + 1 )
        {
          v10 = (unsigned int)(v8 + v7 + 1);
          v11 = GetProcessHeap();
          v12 = (char *)HeapAlloc(v11, 8u, (unsigned int)v10);
          v13 = v12;
          if ( v12 )
          {
            memset_0(v12, 0, (unsigned int)v10);
            if ( v9 )
              StringCchCopyA(v13, v10, v9);
            v14 = 2147483646;
            if ( v10 - 1 <= 0x7FFFFFFE )
            {
              v15 = v10;
              v16 = v13;
              while ( *v16 )
              {
                ++v16;
                if ( !--v15 )
                {
                  v17 = 0;
                  v18 = -2147024809;
                  goto LABEL_30;
                }
              }
              v17 = v10 - v15;
              v18 = 0;
LABEL_30:
              if ( v18 >= 0 )
              {
                v21 = Buffer;
                v22 = &v13[v17];
                for ( i = v10 - v17; i; --i )
                {
                  if ( !v14 )
                    break;
                  if ( !*v21 )
                    break;
                  *v22++ = *v21++;
                  --v14;
                }
                v19 = v22 - 1;
                if ( i )
                  v19 = v22;
                *v19 = 0;
              }
            }
            _InterlockedExchange64((volatile __int64 *)v3, (__int64)v13);
            if ( v9 )
            {
              v20 = GetProcessHeap();
              HeapFree(v20, 0, v9);
            }
          }
          return v3;
        }
        else
        {
          return v3;
        }
      }
      else
      {
        return v3;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000da10  mov     r11, rsp
0x18000da13  mov     [r11+8], rcx
0x18000da17  mov     [r11+10h], rdx
0x18000da1b  mov     [r11+18h], r8
0x18000da1f  mov     [r11+20h], r9
0x18000da23  push    r14
0x18000da25  sub     rsp, 260h
0x18000da2c  mov     rax, cs:__security_cookie
0x18000da33  xor     rax, rsp
0x18000da36  mov     [rsp+268h+var_38], rax
0x18000da3e  xor     r14d, r14d
0x18000da41  test    byte ptr cs:g_WiaTrace_ulFlags, 1
0x18000da48  mov     eax, r14d
0x18000da4b  jz      loc_18000DC25
0x18000da51  mov     [r11-28h], rdi
0x18000da55  call    cs:__imp_GetProcessHeap
0x18000da5b  mov     edx, 8; dwFlags
0x18000da60  mov     r8d, 40h ; '@'; dwBytes
0x18000da66  mov     rcx, rax; hHeap
0x18000da69  call    cs:__imp_HeapAlloc
0x18000da6f  mov     rdi, rax
0x18000da72  test    rax, rax
0x18000da75  jz      loc_18000DC1D
0x18000da7b  xor     edx, edx; Val
0x18000da7d  lea     rcx, [rsp+268h+Buffer]; void *
0x18000da82  mov     r8d, 200h; Size
0x18000da88  call    memset_0
0x18000da8d  xor     edx, edx; Val
0x18000da8f  mov     r8d, 40h ; '@'; Size
0x18000da95  mov     rcx, rdi; void *
0x18000da98  call    memset_0
0x18000da9d  mov     r8, [rsp+268h+Format]; Format
0x18000daa5  lea     r9, [rsp+268h+ArgList]; ArgList
0x18000daad  mov     edx, 1FFh; BufferCount
0x18000dab2  mov     [rsp+268h+var_240], r14
0x18000dab7  lea     rcx, [rsp+268h+Buffer]; Buffer
0x18000dabc  call    _vsnprintf
0x18000dac1  test    eax, eax
0x18000dac3  js      short loc_18000DACC
0x18000dac5  cmp     eax, 1FFh
0x18000daca  jb      short loc_18000DAD4
0x18000dacc  mov     [rsp+268h+var_39], r14b
0x18000dad4  call    cs:__imp_GetCurrentProcessId
0x18000dada  mov     [rdi+0Ch], eax
0x18000dadd  call    cs:__imp_GetCurrentThreadId
0x18000dae3  mov     rcx, cs:?g_WiaTrc_GetIndentLevel@WiaTrcLib@@3P6AKXZEA; ulong (*WiaTrcLib::g_WiaTrc_GetIndentLevel)(void)
0x18000daea  mov     [rdi+10h], eax
0x18000daed  mov     eax, r14d
0x18000daf0  test    rcx, rcx
0x18000daf3  jz      short loc_18000DAFD
0x18000daf5  mov     rax, rcx
0x18000daf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dafd  mov     [rdi+38h], eax
0x18000db00  mov     rax, cs:?g_WiaTrc_GetTraceSettings@WiaTrcLib@@3P6AXPEAK0PEAH@ZEA; void (*WiaTrcLib::g_WiaTrc_GetTraceSettings)(ulong *,ulong *,int *)
0x18000db07  test    rax, rax
0x18000db0a  jnz     loc_18000DC86
0x18000db10  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000db17  lea     rdx, [rsp+268h+Buffer]
0x18000db1c  mov     rax, rcx
0x18000db1f  nop
0x18000db20  inc     rax
0x18000db23  cmp     [rdx+rax], r14b
0x18000db27  jnz     short loc_18000DB20
0x18000db29  test    rax, rax
0x18000db2c  jz      loc_18000DC81
0x18000db32  mov     [rsp+268h+var_20], rsi
0x18000db3a  mov     rsi, [rdi]
0x18000db3d  test    rsi, rsi
0x18000db40  jnz     loc_18000DCD0
0x18000db46  mov     rsi, r14
0x18000db49  mov     ecx, r14d
0x18000db4c  lea     r8d, [rcx+1]
0x18000db50  add     r8d, eax
0x18000db53  jz      loc_18000DCF1
0x18000db59  mov     [rsp+268h+var_10], rbx
0x18000db61  mov     [rsp+268h+var_18], rbp
0x18000db69  mov     ebx, r8d
0x18000db6c  call    cs:__imp_GetProcessHeap
0x18000db72  mov     r8d, ebx; dwBytes
0x18000db75  mov     edx, 8; dwFlags
0x18000db7a  mov     rcx, rax; hHeap
0x18000db7d  call    cs:__imp_HeapAlloc
0x18000db83  mov     rbp, rax
0x18000db86  test    rax, rax
0x18000db89  jz      short loc_18000DC02
0x18000db8b  mov     r8d, ebx; Size
0x18000db8e  xor     edx, edx; Val
0x18000db90  mov     rcx, rax; void *
0x18000db93  call    memset_0
0x18000db98  test    rsi, rsi
0x18000db9b  jnz     loc_18000DCDE
0x18000dba1  lea     rax, [rbx-1]
0x18000dba5  mov     r8d, 7FFFFFFEh
0x18000dbab  cmp     rax, r8
0x18000dbae  ja      short loc_18000DBE6
0x18000dbb0  mov     rcx, rbx
0x18000dbb3  mov     rax, rbp
0x18000dbb6  mov     r9, rbx
0x18000dbb9  nop     dword ptr [rax+00000000h]
0x18000dbc0  cmp     [rax], r14b
0x18000dbc3  jz      short loc_18000DC3F
0x18000dbc5  inc     rax
0x18000dbc8  sub     rcx, 1
0x18000dbcc  jnz     short loc_18000DBC0
0x18000dbce  mov     r9, r14
0x18000dbd1  mov     eax, 80070057h
0x18000dbd6  jmp     short loc_18000DC45
0x18000dbd8  test    rbx, rbx
0x18000dbdb  lea     rax, [rcx-1]
0x18000dbdf  cmovnz  rax, rcx
0x18000dbe3  mov     [rax], r14b
0x18000dbe6  xchg    rbp, [rdi]
0x18000dbe9  test    rsi, rsi
0x18000dbec  jz      short loc_18000DC02
0x18000dbee  call    cs:__imp_GetProcessHeap
0x18000dbf4  mov     r8, rsi; lpMem
0x18000dbf7  xor     edx, edx; dwFlags
0x18000dbf9  mov     rcx, rax; hHeap
0x18000dbfc  call    cs:__imp_HeapFree
0x18000dc02  mov     rbp, [rsp+268h+var_18]
0x18000dc0a  mov     rax, rdi
0x18000dc0d  mov     rbx, [rsp+268h+var_10]
0x18000dc15  mov     rsi, [rsp+268h+var_20]
0x18000dc1d  mov     rdi, [rsp+268h+var_28]
0x18000dc25  mov     rcx, [rsp+268h+var_38]
0x18000dc2d  xor     rcx, rsp; StackCookie
0x18000dc30  call    __security_check_cookie
0x18000dc35  add     rsp, 260h
0x18000dc3c  pop     r14
0x18000dc3e  retn
0x18000dc3f  sub     r9, rcx
0x18000dc42  mov     eax, r14d
0x18000dc45  test    eax, eax
0x18000dc47  js      short loc_18000DBE6
0x18000dc49  lea     rdx, [rsp+268h+Buffer]
0x18000dc4e  lea     rcx, [r9+rbp]
0x18000dc52  sub     rbx, r9
0x18000dc55  jz      short loc_18000DBD8
0x18000dc57  test    r8, r8
0x18000dc5a  jz      loc_18000DBD8
0x18000dc60  movzx   eax, byte ptr [rdx]
0x18000dc63  test    al, al
0x18000dc65  jz      loc_18000DBD8
0x18000dc6b  mov     [rcx], al
0x18000dc6d  inc     rdx
0x18000dc70  inc     rcx
0x18000dc73  dec     r8
0x18000dc76  sub     rbx, 1
0x18000dc7a  jnz     short loc_18000DC57
0x18000dc7c  jmp     loc_18000DBD8
0x18000dc81  mov     rax, rdi
0x18000dc84  jmp     short loc_18000DC1D
0x18000dc86  lea     r8, [rsp+268h+var_248]
0x18000dc8b  mov     [rsp+268h+var_244], r14d
0x18000dc90  lea     rdx, [rsp+268h+var_240]
0x18000dc95  mov     dword ptr [rsp+268h+var_240], r14d
0x18000dc9a  lea     rcx, [rsp+268h+var_244]
0x18000dc9f  mov     [rsp+268h+var_248], r14d
0x18000dca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dca9  cmp     [rsp+268h+var_248], r14d
0x18000dcae  jnz     short loc_18000DCBD
0x18000dcb0  mov     [rdi+34h], r14d
0x18000dcb4  mov     [rdi+3Ch], r14d
0x18000dcb8  jmp     loc_18000DB10
0x18000dcbd  mov     eax, [rsp+268h+var_244]
0x18000dcc1  mov     [rdi+34h], eax
0x18000dcc4  mov     eax, dword ptr [rsp+268h+var_240]
0x18000dcc8  mov     [rdi+3Ch], eax
0x18000dccb  jmp     loc_18000DB10
0x18000dcd0  inc     rcx
0x18000dcd3  cmp     [rsi+rcx], r14b
0x18000dcd7  jnz     short loc_18000DCD0
0x18000dcd9  jmp     loc_18000DB4C
0x18000dcde  mov     r8, rsi; char *
0x18000dce1  mov     rdx, rbx; unsigned __int64
0x18000dce4  mov     rcx, rbp; char *
0x18000dce7  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18000dcec  jmp     loc_18000DBA1
0x18000dcf1  mov     rax, rdi
0x18000dcf4  jmp     loc_18000DC15
```
