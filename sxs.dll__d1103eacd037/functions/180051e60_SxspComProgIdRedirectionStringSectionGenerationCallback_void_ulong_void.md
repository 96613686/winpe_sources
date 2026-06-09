# SxspComProgIdRedirectionStringSectionGenerationCallback(void *,ulong,void *)

- ea: `0x180051e60`
- end: `0x180052025`
- name: `?SxspComProgIdRedirectionStringSectionGenerationCallback@@YAHPEAXK0@Z`
- size: `453`
- prototype: `__int64 __fastcall(void *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a804`
- `0x18000df40`
- `0x180051e60`
- `0x18005d38c`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180051f15`
- `ntdll!RtlPopFrame` at `0x180051f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005200b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005200b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051ee8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051f98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051ee8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051f98`

## pseudocode

```c
__int64 __fastcall SxspComProgIdRedirectionStringSectionGenerationCallback(_QWORD *a1, int a2, _QWORD *a3)
{
  int v6; // edi
  int v7; // edi
  int v8; // edi
  int v9; // edi
  unsigned int v10; // ebx
  _OWORD *v12; // rdx
  __int64 **v13; // rsi
  __int64 v14; // r8
  __int64 *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  DWORD LastError; // eax
  int v19; // [rsp+20h] [rbp-48h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+28h] [rbp-40h] BYREF
  __int64 v21; // [rsp+40h] [rbp-28h]
  int v22; // [rsp+48h] [rbp-20h]
  unsigned int *v23; // [rsp+50h] [rbp-18h]

  v19 = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180072260;
  Frame.Flags = 1;
  v23 = (unsigned int *)&v19;
  Frame.Previous = 0;
  v21 = 544438355;
  v22 = 354;
  CFrame::BaseEnter((CFrame *)&Frame);
  v6 = a2 - 1;
  if ( !v6 )
  {
    a3[1] = 12;
    goto LABEL_6;
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( !v8 )
    {
LABEL_6:
      SetLastError(0);
      *v23 = 1;
      goto LABEL_7;
    }
    v9 = v8 - 1;
    if ( !v9 )
    {
      *a3 = 16LL * a1[6];
      goto LABEL_6;
    }
    if ( v9 == 1 )
    {
      v12 = (_OWORD *)a3[2];
      if ( a3[1] >= (unsigned __int64)(16LL * a1[6]) )
      {
        v13 = (__int64 **)(a1 + 2);
        v14 = 0;
        v15 = *v13;
        while ( v15 && v15 != (__int64 *)v13 )
        {
          *((_DWORD *)v15 + 12) = (_DWORD)v12 - *(_DWORD *)a3;
          *v12 = *((_OWORD *)v15 + 2);
          v15 = (__int64 *)*v15;
          ++v12;
          v14 += 16;
        }
        a3[3] = v14;
        goto LABEL_6;
      }
    }
    SetLastError(0x54Fu);
    *v23 = 0;
  }
  else
  {
    if ( a3[2] >= 0xCu )
    {
      v16 = a3[1];
      v17 = a3[3];
      *(_QWORD *)v17 = 12;
      *(_DWORD *)(v17 + 8) = *(_DWORD *)(v16 + 48);
      a3[4] = 12;
      goto LABEL_6;
    }
    CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&Frame, 0x7Au);
    FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_18007B680);
  }
LABEL_7:
  v10 = *v23;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v10 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v10;
}

```

## disassembly

```asm
0x180051e60  push    rbp
0x180051e62  push    rbx
0x180051e63  push    rsi
0x180051e64  push    rdi
0x180051e65  mov     rbp, rsp
0x180051e68  sub     rsp, 68h
0x180051e6c  mov     rax, cs:__security_cookie
0x180051e73  xor     rax, rsp
0x180051e76  mov     [rbp+var_10], rax
0x180051e7a  lea     rax, qword_180072260
0x180051e81  mov     [rbp+var_48], 0
0x180051e88  mov     [rbp+Frame.Context], rax
0x180051e8c  mov     rsi, rcx
0x180051e8f  lea     rax, [rbp+var_48]
0x180051e93  mov     [rbp+Frame.Flags], 1
0x180051e9a  lea     rcx, [rbp+Frame]; this
0x180051e9e  mov     [rbp+var_18], rax
0x180051ea2  mov     rbx, r8
0x180051ea5  mov     [rbp+Frame.Previous], 0
0x180051ead  mov     edi, edx
0x180051eaf  mov     [rbp+var_28], 20737853h
0x180051eb7  mov     [rbp+var_20], 162h
0x180051ebe  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180051ec3  sub     edi, 1
0x180051ec6  jz      short loc_180051F39
0x180051ec8  sub     edi, 1
0x180051ecb  jz      loc_180051FB3
0x180051ed1  sub     edi, 1
0x180051ed4  jz      short loc_180051EE6
0x180051ed6  sub     edi, 1
0x180051ed9  jnz     short loc_180051F43
0x180051edb  mov     rax, [rsi+30h]
0x180051edf  shl     rax, 4
0x180051ee3  mov     [rbx], rax
0x180051ee6  xor     ecx, ecx; dwErrCode
0x180051ee8  call    cs:__imp_SetLastError
0x180051eef  nop     dword ptr [rax+rax+00h]
0x180051ef4  mov     rax, [rbp+var_18]
0x180051ef8  mov     dword ptr [rax], 1
0x180051efe  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180051f05  mov     rax, [rbp+var_18]
0x180051f09  mov     ebx, [rax]
0x180051f0b  jnz     loc_180051FFB
0x180051f11  lea     rcx, [rbp+Frame]; Frame
0x180051f15  call    cs:__imp_RtlPopFrame
0x180051f1c  nop     dword ptr [rax+rax+00h]
0x180051f21  mov     eax, ebx
0x180051f23  mov     rcx, [rbp+var_10]
0x180051f27  xor     rcx, rsp; StackCookie
0x180051f2a  call    __security_check_cookie
0x180051f2f  add     rsp, 68h
0x180051f33  pop     rdi
0x180051f34  pop     rsi
0x180051f35  pop     rbx
0x180051f36  pop     rbp
0x180051f37  retn
0x180051f39  mov     qword ptr [rbx+8], 0Ch
0x180051f41  jmp     short loc_180051EE6
0x180051f43  cmp     edi, 1
0x180051f46  jnz     short loc_180051F93
0x180051f48  mov     rax, [rsi+30h]
0x180051f4c  mov     rdx, [rbx+10h]
0x180051f50  shl     rax, 4
0x180051f54  cmp     [rbx+8], rax
0x180051f58  jb      short loc_180051F93
0x180051f5a  add     rsi, 10h
0x180051f5e  xor     r8d, r8d
0x180051f61  mov     rcx, [rsi]
0x180051f64  test    rcx, rcx
0x180051f67  jz      short loc_180051F6E
0x180051f69  cmp     rcx, rsi
0x180051f6c  jnz     short loc_180051F77
0x180051f6e  mov     [rbx+18h], r8
0x180051f72  jmp     loc_180051EE6
0x180051f77  mov     eax, edx
0x180051f79  sub     eax, [rbx]
0x180051f7b  mov     [rcx+30h], eax
0x180051f7e  movups  xmm0, xmmword ptr [rcx+20h]
0x180051f82  movdqu  xmmword ptr [rdx], xmm0
0x180051f86  mov     rcx, [rcx]
0x180051f89  add     rdx, 10h
0x180051f8d  add     r8, 10h
0x180051f91  jmp     short loc_180051F64
0x180051f93  mov     ecx, 54Fh; dwErrCode
0x180051f98  call    cs:__imp_SetLastError
0x180051f9f  nop     dword ptr [rax+rax+00h]
0x180051fa4  mov     rax, [rbp+var_18]
0x180051fa8  mov     dword ptr [rax], 0
0x180051fae  jmp     loc_180051EFE
0x180051fb3  cmp     qword ptr [rbx+10h], 0Ch
0x180051fb8  jnb     short loc_180051FD9
0x180051fba  mov     edx, 7Ah ; 'z'; unsigned int
0x180051fbf  lea     rcx, [rbp+Frame]; this
0x180051fc3  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x180051fc8  lea     rcx, off_18007B680; struct _CALL_SITE_INFO *
0x180051fcf  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180051fd4  jmp     loc_180051EFE
0x180051fd9  mov     rax, [rbx+8]
0x180051fdd  mov     rcx, [rbx+18h]
0x180051fe1  mov     qword ptr [rcx], 0Ch
0x180051fe8  mov     eax, [rax+30h]
0x180051feb  mov     [rcx+8], eax
0x180051fee  mov     qword ptr [rbx+20h], 0Ch
0x180051ff6  jmp     loc_180051EE6
0x180051ffb  test    ebx, ebx
0x180051ffd  jz      short loc_18005200B
0x180051fff  xor     ecx, ecx; char *
0x180052001  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180052006  jmp     loc_180051F11
0x18005200b  call    cs:__imp_GetLastError
0x180052012  nop     dword ptr [rax+rax+00h]
0x180052017  mov     ecx, eax; unsigned int
0x180052019  xor     edx, edx; Format
0x18005201b  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180052020  jmp     loc_180051F11
```
