# FreeRepairInfos(tagRepairInfo *,ulong,int)

- ea: `0x1800120e8`
- end: `0x180012216`
- name: `?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z`
- size: `302`
- prototype: `void __fastcall(struct tagRepairInfo *pv, unsigned int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180007800`

## callees

- `0x1800120e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001211b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012135`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012160`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012178`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012190`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800121a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800121cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800121fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001211b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012135`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012160`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012178`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012190`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800121a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800121cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800121fc`

## pseudocode

```c
void __fastcall FreeRepairInfos(struct tagRepairInfo *pv, unsigned int a2, int a3)
{
  unsigned int v6; // esi
  __int64 v7; // rbp
  __int64 v8; // rbx
  LPWSTR pwszDescription; // rcx
  UiInfo *p_UiInfo; // rbx
  LPWSTR pwszFile; // rcx
  LPWSTR pwzNull; // rcx
  LPWSTR pwszParameters; // rcx

  if ( pv && a2 )
  {
    v6 = 0;
    v7 = 0;
    do
    {
      v8 = v7;
      CoTaskMemFree(pv[v7].pwszClassName);
      pwszDescription = pv[v7].pwszDescription;
      pv[v8].pwszClassName = 0;
      CoTaskMemFree(pwszDescription);
      pv[v8].pwszDescription = 0;
      p_UiInfo = &pv[v7].UiInfo;
      if ( p_UiInfo )
      {
        if ( p_UiInfo->type == UIT_SHELL_COMMAND )
        {
          CoTaskMemFree(p_UiInfo->ShellInfo.pwszDirectory);
          pwszFile = p_UiInfo->ShellInfo.pwszFile;
          p_UiInfo->ShellInfo.pwszDirectory = 0;
          CoTaskMemFree(pwszFile);
          pwzNull = p_UiInfo->pwzNull;
          p_UiInfo->ShellInfo.pwszFile = 0;
          CoTaskMemFree(pwzNull);
          pwszParameters = p_UiInfo->ShellInfo.pwszParameters;
          p_UiInfo->pwzNull = 0;
          CoTaskMemFree(pwszParameters);
          p_UiInfo->ShellInfo.pwszParameters = 0;
        }
        else if ( p_UiInfo->type == UIT_HELP_PANE || p_UiInfo->type == UIT_DUI )
        {
          CoTaskMemFree(p_UiInfo->pwzNull);
          p_UiInfo->pwzNull = 0;
        }
        p_UiInfo->type = UIT_NONE;
      }
      ++v6;
      ++v7;
    }
    while ( v6 < a2 );
    if ( a3 )
      CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x1800120e8  test    rcx, rcx
0x1800120eb  jz      locret_180012214
0x1800120f1  push    rbx
0x1800120f2  push    rbp
0x1800120f3  push    rsi
0x1800120f4  push    rdi
0x1800120f5  push    r14
0x1800120f7  push    r15
0x1800120f9  sub     rsp, 28h
0x1800120fd  mov     r15d, r8d
0x180012100  mov     r14d, edx
0x180012103  mov     rdi, rcx
0x180012106  test    edx, edx
0x180012108  jz      loc_180012208
0x18001210e  xor     esi, esi
0x180012110  xor     ebp, ebp
0x180012112  imul    rbx, rbp, 70h ; 'p'
0x180012116  mov     rcx, [rbx+rdi+10h]; pv
0x18001211b  call    cs:__imp_CoTaskMemFree
0x180012122  nop     dword ptr [rax+rax+00h]
0x180012127  mov     rcx, [rbx+rdi+18h]; pv
0x18001212c  mov     qword ptr [rbx+rdi+10h], 0
0x180012135  call    cs:__imp_CoTaskMemFree
0x18001213c  nop     dword ptr [rax+rax+00h]
0x180012141  mov     qword ptr [rbx+rdi+18h], 0
0x18001214a  add     rbx, 38h ; '8'
0x18001214e  add     rbx, rdi
0x180012151  jz      loc_1800121E6
0x180012157  cmp     dword ptr [rbx], 2
0x18001215a  jnz     short loc_1800121BE
0x18001215c  mov     rcx, [rbx+20h]; pv
0x180012160  call    cs:__imp_CoTaskMemFree
0x180012167  nop     dword ptr [rax+rax+00h]
0x18001216c  mov     rcx, [rbx+10h]; pv
0x180012170  mov     qword ptr [rbx+20h], 0
0x180012178  call    cs:__imp_CoTaskMemFree
0x18001217f  nop     dword ptr [rax+rax+00h]
0x180012184  mov     rcx, [rbx+8]; pv
0x180012188  mov     qword ptr [rbx+10h], 0
0x180012190  call    cs:__imp_CoTaskMemFree
0x180012197  nop     dword ptr [rax+rax+00h]
0x18001219c  mov     rcx, [rbx+18h]; pv
0x1800121a0  mov     qword ptr [rbx+8], 0
0x1800121a8  call    cs:__imp_CoTaskMemFree
0x1800121af  nop     dword ptr [rax+rax+00h]
0x1800121b4  mov     qword ptr [rbx+18h], 0
0x1800121bc  jmp     short loc_1800121E0
0x1800121be  cmp     dword ptr [rbx], 3
0x1800121c1  jz      short loc_1800121C8
0x1800121c3  cmp     dword ptr [rbx], 4
0x1800121c6  jnz     short loc_1800121E0
0x1800121c8  mov     rcx, [rbx+8]; pv
0x1800121cc  call    cs:__imp_CoTaskMemFree
0x1800121d3  nop     dword ptr [rax+rax+00h]
0x1800121d8  mov     qword ptr [rbx+8], 0
0x1800121e0  mov     dword ptr [rbx], 1
0x1800121e6  inc     esi
0x1800121e8  inc     rbp
0x1800121eb  cmp     esi, r14d
0x1800121ee  jb      loc_180012112
0x1800121f4  test    r15d, r15d
0x1800121f7  jz      short loc_180012208
0x1800121f9  mov     rcx, rdi; pv
0x1800121fc  call    cs:__imp_CoTaskMemFree
0x180012203  nop     dword ptr [rax+rax+00h]
0x180012208  add     rsp, 28h
0x18001220c  pop     r15
0x18001220e  pop     r14
0x180012210  pop     rdi
0x180012211  pop     rsi
0x180012212  pop     rbp
0x180012213  pop     rbx
0x180012214  retn
```
