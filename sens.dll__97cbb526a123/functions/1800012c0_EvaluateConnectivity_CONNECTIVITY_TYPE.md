# EvaluateConnectivity(CONNECTIVITY_TYPE)

- ea: `0x1800012c0`
- end: `0x180001349`
- name: `?EvaluateConnectivity@@YAXW4CONNECTIVITY_TYPE@@@Z`
- size: `137`
- prototype: `int __fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001040`
- `0x1800010f0`

## callees

- `0x1800012c0`
- `0x180008300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001322`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800012d8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800012d8`

## pseudocode

```c
int __fastcall EvaluateConnectivity(int a1)
{
  ULONG (__stdcall *v1)(PVOID); // rcx
  int result; // eax
  DWORD LastError; // eax

  if ( a1 == 4 )
  {
    v1 = EvaluateLanConnectivityDelayed;
  }
  else if ( a1 == 2 )
  {
    v1 = (ULONG (__stdcall *)(PVOID))EvaluateWanConnectivity;
  }
  else
  {
    v1 = EvaluateLanConnectivity;
  }
  result = QueueUserWorkItem(v1, 0, 0x10u);
  if ( !result )
  {
    result = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      return WPP_SF_d(
               *((_QWORD *)WPP_GLOBAL_Control + 2),
               14,
               WPP_7617987f8fa93304f2df28234d8870cd_Traceguids,
               LastError);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800012c0  sub     rsp, 28h
0x1800012c4  cmp     ecx, 4
0x1800012c7  jnz     short loc_1800012E7
0x1800012c9  lea     rcx, ?EvaluateLanConnectivityDelayed@@YAHPEAK@Z; Function
0x1800012d0  xor     edx, edx; Context
0x1800012d2  mov     r8d, 10h; Flags
0x1800012d8  call    cs:__imp_QueueUserWorkItem
0x1800012de  test    eax, eax
0x1800012e0  jz      short loc_180001303
0x1800012e2  add     rsp, 28h
0x1800012e6  retn
0x1800012e7  sub     ecx, 1
0x1800012ea  jnz     short loc_1800012F5
0x1800012ec  lea     rcx, ?EvaluateLanConnectivity@@YAHPEAK@Z; EvaluateLanConnectivity(ulong *)
0x1800012f3  jmp     short loc_1800012D0
0x1800012f5  cmp     ecx, 1
0x1800012f8  jnz     short loc_1800012EC
0x1800012fa  lea     rcx, ?EvaluateWanConnectivity@@YAHPEAK@Z; EvaluateWanConnectivity(ulong *)
0x180001301  jmp     short loc_1800012D0
0x180001303  mov     rax, cs:WPP_GLOBAL_Control
0x18000130a  lea     rcx, WPP_GLOBAL_Control
0x180001311  cmp     rax, rcx
0x180001314  jz      short loc_1800012E2
0x180001316  test    byte ptr [rax+1Ch], 1
0x18000131a  jz      short loc_1800012E2
0x18000131c  cmp     byte ptr [rax+19h], 2
0x180001320  jb      short loc_1800012E2
0x180001322  call    cs:__imp_GetLastError
0x180001328  mov     rcx, cs:WPP_GLOBAL_Control
0x18000132f  lea     r8, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids
0x180001336  mov     edx, 0Eh
0x18000133b  mov     r9d, eax
0x18000133e  mov     rcx, [rcx+10h]
0x180001342  call    WPP_SF_d
0x180001347  jmp     short loc_1800012E2
```
