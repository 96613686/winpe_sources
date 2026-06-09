# _lambda_cd2099a84e29dd60a3ce15c92771ff9c_::_lambda_invoker_cdecl_

- ea: `0x18000c940`
- end: `0x18000c9cf`
- name: `_lambda_cd2099a84e29dd60a3ce15c92771ff9c_::_lambda_invoker_cdecl_`
- size: `143`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a374`
- `0x18000c940`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18000c984`
- `ntdll!RtlGetPersistedStateLocation` at `0x18000c984`
- `ntdll!RtlNtStatusToDosError` at `0x18000c98c`
- `ntdll!RtlNtStatusToDosError` at `0x18000c98c`

## string_xrefs

- `0x18000c9aa`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`

## pseudocode

```c
_BOOL8 __fastcall lambda_cd2099a84e29dd60a3ce15c92771ff9c_::_lambda_invoker_cdecl_(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  __int64 v3; // rcx
  NTSTATUS PersistedStateLocation; // eax
  signed int v5; // eax
  signed int v6; // ebx
  __int64 *v8; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v3 = 69LL * (_QWORD)Parameter;
  v8 = &qword_180015188[69 * (_QWORD)Parameter + 1];
  off_180015170[v3 + 3] = (wchar_t *)Parameter;
  PersistedStateLocation = RtlGetPersistedStateLocation(off_180015170[v3], 0, off_180015170[v3 + 1], 0);
  v5 = RtlNtStatusToDosError(PersistedStateLocation);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
    v6 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\regredirect.cxx",
      (const char *)(unsigned int)v6,
      (int)v8);
  return v6 >= 0;
}

```

## disassembly

```asm
0x18000c940  push    rbx
0x18000c942  sub     rsp, 40h
0x18000c946  imul    rcx, rdx, 228h
0x18000c94d  lea     r10, off_180015170; "WSearch"
0x18000c954  mov     [rsp+48h+var_18], 0
0x18000c95d  lea     rax, [r10+20h]
0x18000c961  mov     [rsp+48h+var_20], 208h
0x18000c969  add     rax, rcx
0x18000c96c  xor     r9d, r9d
0x18000c96f  mov     qword ptr [rsp+48h+var_28], rax; int
0x18000c974  mov     [rcx+r10+18h], rdx
0x18000c979  xor     edx, edx
0x18000c97b  mov     r8, [rcx+r10+8]
0x18000c980  mov     rcx, [rcx+r10]
0x18000c984  call    cs:__imp_RtlGetPersistedStateLocation
0x18000c98a  mov     ecx, eax; Status
0x18000c98c  call    cs:__imp_RtlNtStatusToDosError
0x18000c992  mov     ebx, eax
0x18000c994  test    eax, eax
0x18000c996  jle     short loc_18000C9A1
0x18000c998  movzx   ebx, ax
0x18000c99b  or      ebx, 80070000h
0x18000c9a1  test    ebx, ebx
0x18000c9a3  jns     short loc_18000C9C0
0x18000c9a5  mov     rcx, [rsp+48h]; this
0x18000c9aa  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\com"...
0x18000c9b1  mov     r9d, ebx; char *
0x18000c9b4  mov     edx, 36h ; '6'; void *
0x18000c9b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c9be  jmp     short loc_18000C9C2
0x18000c9c0  xor     ebx, ebx
0x18000c9c2  not     ebx
0x18000c9c4  shr     ebx, 1Fh
0x18000c9c7  mov     eax, ebx
0x18000c9c9  add     rsp, 40h
0x18000c9cd  pop     rbx
0x18000c9ce  retn
```
