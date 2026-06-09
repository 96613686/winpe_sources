# WiaTrace_Trace(ushort const *,...)

- ea: `0x180004380`
- end: `0x1800044d2`
- name: `?WiaTrace_Trace@@YAPEAUtagWiaTraceData_Type@@PEBGZZ`
- size: `338`
- prototype: `struct tagWiaTraceData_Type *(const unsigned __int16 *, ...)`
- caller_count: `21`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000301c`
- `0x1800030f0`
- `0x180003374`
- `0x1800033f4`
- `0x18000426c`
- `0x180004aa8`
- `0x180005f04`
- `0x180024cb0`
- `0x180030980`
- `0x1800315a0`
- `0x180039664`
- `0x180051c60`
- `0x1800533a4`
- `0x180054fe4`
- `0x180059ed4`
- `0x180065bb0`
- `0x180065dec`
- `0x180069b10`
- `0x180076bc8`
- `0x180076df8`
- `0x180077040`

## callees

- `0x180004380`
- `0x180004680`
- `0x18002f424`
- `0x180033cc0`
- `0x180034658`
- `0x180034664`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800043b4`
- `KERNEL32!GetProcessHeap` at `0x1800043b4`
- `KERNEL32!GetCurrentProcessId` at `0x180004432`
- `KERNEL32!GetCurrentProcessId` at `0x180004432`
- `KERNEL32!GetCurrentThreadId` at `0x18000443b`
- `KERNEL32!GetCurrentThreadId` at `0x18000443b`
- `KERNEL32!HeapAlloc` at `0x1800043c6`
- `KERNEL32!HeapAlloc` at `0x1800043c6`

## pseudocode

```c
struct tagWiaTraceData_Type *WiaTrace_Trace(const unsigned __int16 *a1, ...)
{
  HANDLE ProcessHeap; // rax
  _DWORD *v2; // rbx
  WiaTrcLib *v3; // rcx
  unsigned __int16 *v4; // r8
  __int64 v6; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v7; // [rsp+30h] [rbp-D8h] BYREF
  wchar_t Buffer[512]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 Args; // [rsp+470h] [rbp+368h] BYREF
  va_list Argsa; // [rsp+470h] [rbp+368h]
  __int64 v12; // [rsp+478h] [rbp+370h]
  va_list va1; // [rsp+480h] [rbp+378h] BYREF

  va_start(va1, a1);
  va_start(Argsa, a1);
  Args = va_arg(va1, _QWORD);
  v12 = va_arg(va1, _QWORD);
  ProcessHeap = GetProcessHeap();
  v2 = HeapAlloc(ProcessHeap, 8u, 0x40u);
  if ( v2 )
  {
    memset_0(Buffer, 0, sizeof(Buffer));
    memset_0(v2, 0, 0x40u);
    v7 = 0;
    if ( (unsigned int)vsnwprintf(Buffer, 0x1FFu, a1, Argsa) > 0x1FE )
      Buffer[511] = 0;
    v2[3] = GetCurrentProcessId();
    v2[4] = GetCurrentThreadId();
    v2[14] = WiaTrcLib::GetCurrentIndentLevel(v3);
    if ( WiaTrcLib::g_WiaTrc_GetTraceSettings )
    {
      LODWORD(v7) = 0;
      v6 = 0;
      WiaTrcLib::g_WiaTrc_GetTraceSettings((unsigned int *)&v6 + 1, (unsigned int *)&v7, (int *)&v6);
      if ( (_DWORD)v6 )
      {
        v2[13] = HIDWORD(v6);
        v2[15] = v7;
      }
      else
      {
        v2[13] = 0;
        v2[15] = 0;
      }
    }
    WiaTrcLib::AddToString((WiaTrcLib *)v2, Buffer, v4);
  }
  return (struct tagWiaTraceData_Type *)v2;
}

```

## disassembly

```asm
0x180004380  mov     rax, rsp
0x180004383  mov     [rax+8], rcx
0x180004387  mov     [rax+10h], rdx
0x18000438b  mov     [rax+18h], r8
0x18000438f  mov     [rax+20h], r9
0x180004393  push    rbp
0x180004394  push    rbx
0x180004395  lea     rbp, [rax-358h]
0x18000439c  sub     rsp, 448h
0x1800043a3  mov     rax, cs:__security_cookie
0x1800043aa  xor     rax, rsp
0x1800043ad  mov     [rbp+350h+var_20], rax
0x1800043b4  call    cs:__imp_GetProcessHeap
0x1800043ba  mov     edx, 8; dwFlags
0x1800043bf  mov     rcx, rax; hHeap
0x1800043c2  lea     r8d, [rdx+38h]; dwBytes
0x1800043c6  call    cs:__imp_HeapAlloc
0x1800043cc  mov     rbx, rax
0x1800043cf  test    rax, rax
0x1800043d2  jz      loc_1800044B6
0x1800043d8  xor     edx, edx; Val
0x1800043da  lea     rcx, [rsp+450h+Buffer]; void *
0x1800043df  mov     r8d, 400h; Size
0x1800043e5  call    memset_0
0x1800043ea  xor     edx, edx; Val
0x1800043ec  mov     rcx, rbx; void *
0x1800043ef  lea     r8d, [rdx+40h]; Size
0x1800043f3  call    memset_0
0x1800043f8  mov     r8, [rbp+350h+Format]; Format
0x1800043ff  lea     r9, [rbp+350h+Args]; Args
0x180004406  mov     edx, 1FFh; BufferCount
0x18000440b  mov     [rsp+450h+var_428], 0
0x180004414  lea     rcx, [rsp+450h+Buffer]; Buffer
0x180004419  call    _vsnwprintf
0x18000441e  test    eax, eax
0x180004420  js      short loc_180004429
0x180004422  cmp     eax, 1FFh
0x180004427  jb      short loc_180004432
0x180004429  xor     eax, eax
0x18000442b  mov     [rbp+350h+var_22], ax
0x180004432  call    cs:__imp_GetCurrentProcessId
0x180004438  mov     [rbx+0Ch], eax
0x18000443b  call    cs:__imp_GetCurrentThreadId
0x180004441  mov     [rbx+10h], eax
0x180004444  call    ?GetCurrentIndentLevel@WiaTrcLib@@YAKXZ; WiaTrcLib::GetCurrentIndentLevel(void)
0x180004449  mov     [rbx+38h], eax
0x18000444c  mov     rax, cs:?g_WiaTrc_GetTraceSettings@WiaTrcLib@@3P6AXPEAK0PEAH@ZEA; void (*WiaTrcLib::g_WiaTrc_GetTraceSettings)(ulong *,ulong *,int *)
0x180004453  test    rax, rax
0x180004456  jz      short loc_1800044A9
0x180004458  lea     r8, [rsp+450h+var_430]
0x18000445d  mov     dword ptr [rsp+450h+var_430+4], 0
0x180004465  lea     rdx, [rsp+450h+var_428]
0x18000446a  mov     dword ptr [rsp+450h+var_428], 0
0x180004472  lea     rcx, [rsp+450h+var_430+4]
0x180004477  mov     dword ptr [rsp+450h+var_430], 0
0x18000447f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004484  cmp     dword ptr [rsp+450h+var_430], 0
0x180004489  jz      short loc_18000449B
0x18000448b  mov     eax, dword ptr [rsp+450h+var_430+4]
0x18000448f  mov     [rbx+34h], eax
0x180004492  mov     eax, dword ptr [rsp+450h+var_428]
0x180004496  mov     [rbx+3Ch], eax
0x180004499  jmp     short loc_1800044A9
0x18000449b  mov     dword ptr [rbx+34h], 0
0x1800044a2  mov     dword ptr [rbx+3Ch], 0
0x1800044a9  lea     rdx, [rsp+450h+Buffer]; lpWideCharStr
0x1800044ae  mov     rcx, rbx; this
0x1800044b1  call    ?AddToString@WiaTrcLib@@YAJPEAPEADPEAG@Z; WiaTrcLib::AddToString(char * *,ushort *)
0x1800044b6  mov     rax, rbx
0x1800044b9  mov     rcx, [rbp+350h+var_20]
0x1800044c0  xor     rcx, rsp; StackCookie
0x1800044c3  call    __security_check_cookie
0x1800044c8  add     rsp, 448h
0x1800044cf  pop     rbx
0x1800044d0  pop     rbp
0x1800044d1  retn
```
