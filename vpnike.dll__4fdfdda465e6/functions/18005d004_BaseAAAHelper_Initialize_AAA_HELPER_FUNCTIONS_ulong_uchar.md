# BaseAAAHelper::Initialize(_AAA_HELPER_FUNCTIONS *,ulong,uchar)

- ea: `0x18005d004`
- end: `0x18005d12c`
- name: `?Initialize@BaseAAAHelper@@QEAAXPEAU_AAA_HELPER_FUNCTIONS@@KE@Z`
- size: `296`
- prototype: `void __fastcall(BaseAAAHelper *this, struct _AAA_HELPER_FUNCTIONS *, int, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180004640`

## callees

- `0x1800077bc`
- `0x18005d004`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d0a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d0da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d0a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d0da`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x18005d074`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x18005d074`

## string_xrefs

- `0x18005d0e3`: `GetComputerName failed = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall BaseAAAHelper::Initialize(BaseAAAHelper *this, struct _AAA_HELPER_FUNCTIONS *a2, int a3, char a4)
{
  __int128 v4; // xmm0
  __int64 v6; // xmm1_8
  DWORD LastError; // eax
  DWORD v8; // eax
  DWORD nSize[4]; // [rsp+20h] [rbp-828h] BYREF
  int v10; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v11[2044]; // [rsp+34h] [rbp-814h] BYREF

  v4 = *(_OWORD *)a2;
  v10 = 0;
  *(_OWORD *)((char *)this + 8) = v4;
  *(_OWORD *)((char *)this + 24) = *((_OWORD *)a2 + 1);
  *(_OWORD *)((char *)this + 40) = *((_OWORD *)a2 + 2);
  v6 = *((_QWORD *)a2 + 6);
  *((_DWORD *)this + 20) = a3;
  *((_QWORD *)this + 7) = v6;
  *((_BYTE *)this + 84) = a4;
  memset_0(v11, 0, sizeof(v11));
  nSize[0] = 16;
  if ( !GetComputerNameA((LPSTR)this + 64, nSize) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_73a80652a3813123eeef9a786157437c_Traceguids, LastError);
    }
    if ( (_QWORD)xmmword_1800AABC0 )
    {
      LOWORD(v10) = 0;
      v8 = GetLastError();
      FormatRRASErrorString(&v10, L"GetComputerName failed = %d", v8);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
        gBaseEtwContext,
        xmmword_1800AABC0,
        &v10);
    }
  }
}

```

## disassembly

```asm
0x18005d004  push    rbx
0x18005d006  sub     rsp, 840h
0x18005d00d  mov     rax, cs:__security_cookie
0x18005d014  xor     rax, rsp
0x18005d017  mov     [rsp+848h+var_18], rax
0x18005d01f  movups  xmm0, xmmword ptr [rdx]
0x18005d022  mov     rbx, rcx
0x18005d025  xor     eax, eax
0x18005d027  mov     [rsp+848h+var_818], eax
0x18005d02b  movups  xmmword ptr [rcx+8], xmm0
0x18005d02f  movups  xmm1, xmmword ptr [rdx+10h]
0x18005d033  movups  xmmword ptr [rcx+18h], xmm1
0x18005d037  movups  xmm0, xmmword ptr [rdx+20h]
0x18005d03b  movups  xmmword ptr [rcx+28h], xmm0
0x18005d03f  movsd   xmm1, qword ptr [rdx+30h]
0x18005d044  xor     edx, edx; Val
0x18005d046  mov     [rcx+50h], r8d
0x18005d04a  mov     r8d, 7FCh; Size
0x18005d050  movsd   qword ptr [rcx+38h], xmm1
0x18005d055  mov     [rcx+54h], r9b
0x18005d059  lea     rcx, [rsp+848h+var_814]; void *
0x18005d05e  call    memset_0
0x18005d063  lea     rcx, [rbx+40h]; lpBuffer
0x18005d067  mov     [rsp+848h+nSize], 10h
0x18005d06f  lea     rdx, [rsp+848h+nSize]; nSize
0x18005d074  call    cs:__imp_GetComputerNameA
0x18005d07a  test    eax, eax
0x18005d07c  jnz     loc_18005D113
0x18005d082  mov     rax, cs:WPP_GLOBAL_Control
0x18005d089  lea     rcx, WPP_GLOBAL_Control
0x18005d090  cmp     rax, rcx
0x18005d093  jz      short loc_18005D0C9
0x18005d095  test    dword ptr [rax+1Ch], 800000h
0x18005d09c  jz      short loc_18005D0C9
0x18005d09e  cmp     byte ptr [rax+19h], 3
0x18005d0a2  jb      short loc_18005D0C9
0x18005d0a4  call    cs:__imp_GetLastError
0x18005d0aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d0b1  lea     r8, WPP_73a80652a3813123eeef9a786157437c_Traceguids
0x18005d0b8  mov     edx, 0Fh
0x18005d0bd  mov     r9d, eax
0x18005d0c0  mov     rcx, [rcx+10h]
0x18005d0c4  call    WPP_SF_d
0x18005d0c9  cmp     qword ptr cs:xmmword_1800AABC0, 0
0x18005d0d1  jz      short loc_18005D113
0x18005d0d3  xor     eax, eax
0x18005d0d5  mov     word ptr [rsp+848h+var_818], ax
0x18005d0da  call    cs:__imp_GetLastError
0x18005d0e0  mov     r8d, eax
0x18005d0e3  lea     rdx, aGetcomputernam; "GetComputerName failed = %d"
0x18005d0ea  lea     rcx, [rsp+848h+var_818]
0x18005d0ef  call    FormatRRASErrorString
0x18005d0f4  mov     rdx, qword ptr cs:xmmword_1800AABC0
0x18005d0fb  lea     r8, [rsp+848h+var_818]
0x18005d100  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18005d107  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005d10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d113  mov     rcx, [rsp+848h+var_18]
0x18005d11b  xor     rcx, rsp; StackCookie
0x18005d11e  call    __security_check_cookie
0x18005d123  add     rsp, 840h
0x18005d12a  pop     rbx
0x18005d12b  retn
```
