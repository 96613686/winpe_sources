# CSSGenCtx::Create(_STRING_SECTION_GENERATION_CONTEXT * *,ulong,int,int (*)(void *,ulong,void *),void *)

- ea: `0x180045460`
- end: `0x180045711`
- name: `?Create@CSSGenCtx@@SAHPEAPEAU_STRING_SECTION_GENERATION_CONTEXT@@KHP6AHPEAXK1@Z1@Z`
- size: `689`
- prototype: `__int64 __fastcall(struct _STRING_SECTION_GENERATION_CONTEXT **, unsigned int, int, int (*)(void *, unsigned int, void *), void *)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180011de0`
- `0x1800143e0`
- `0x18001f2c0`
- `0x1800278b0`
- `0x180044820`

## callees

- `0x18001c2c8`
- `0x180045460`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180045579`
- `ntdll!RtlPopFrame` at `0x180045579`
- `ntdll!_snprintf_s` at `0x180045627`
- `ntdll!_snprintf_s` at `0x180045627`
- `ntdll!RtlGetFrame` at `0x1800455cb`
- `ntdll!RtlGetFrame` at `0x1800455cb`
- `ntdll!RtlPushFrame` at `0x1800454d1`
- `ntdll!RtlPushFrame` at `0x1800454d1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180045643`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180045643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800455ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800456f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800455ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800456f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004553c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045651`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045662`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004553c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045651`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045662`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800454f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800454f9`

## pseudocode

```c
__int64 __fastcall CSSGenCtx::Create(
        struct _STRING_SECTION_GENERATION_CONTEXT **a1,
        __int64 a2,
        __int64 a3,
        int (*a4)(void *, unsigned int, void *),
        void *a5)
{
  unsigned int v6; // ebx
  _BYTE *v8; // rax
  int Previous; // edi
  const char *v11; // rsi
  const char *FrameName; // rbp
  PTEB_ACTIVE_FRAME v13; // rax
  PTEB_ACTIVE_FRAME v14; // rcx
  DWORD LastError; // ebx
  PCTEB_ACTIVE_FRAME_CONTEXT Context; // rdx
  DWORD v17; // eax
  int v18; // [rsp+40h] [rbp-268h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+48h] [rbp-260h] BYREF
  __int64 v20; // [rsp+60h] [rbp-248h]
  int v21; // [rsp+68h] [rbp-240h]
  int *v22; // [rsp+70h] [rbp-238h]
  char Buffer[512]; // [rsp+80h] [rbp-228h] BYREF

  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180071390;
  v18 = 0;
  v6 = 1;
  Frame.Previous = 0;
  v22 = &v18;
  Frame.Flags = 1;
  v20 = 544438355;
  v21 = 46;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v8 = HeapAlloc(g_hHeap, 0, 0x38u);
  if ( v8 )
  {
    v8[52] = 0;
    *((_QWORD *)v8 + 3) = 0;
    *((_QWORD *)v8 + 4) = 0;
    *((_DWORD *)v8 + 4) = 0;
    *((_DWORD *)v8 + 12) = 0;
    *((_QWORD *)v8 + 1) = a5;
    *(_QWORD *)v8 = a4;
    v8[44] = 1;
    *((_DWORD *)v8 + 10) = 1;
    *a1 = (struct _STRING_SECTION_GENERATION_CONTEXT *)v8;
    SetLastError(0);
    *v22 = 1;
    goto LABEL_5;
  }
  Previous = 0;
  v11 = byte_18008517D;
  FrameName = byte_18008517D;
  v13 = RtlGetFrame();
  if ( v13 && (v13->Flags & 1) != 0 )
  {
    v14 = v13;
    goto LABEL_12;
  }
  v14 = 0;
  if ( v13 )
  {
LABEL_12:
    Context = v13->Context;
    if ( Context )
    {
      if ( Context->FrameName )
        FrameName = Context->FrameName;
      if ( (Context->Flags & 1) != 0 && *(_QWORD *)&Context[1].Flags )
        v11 = *(const char **)&Context[1].Flags;
    }
    if ( v14 && *(_QWORD *)&v14[1].Flags == 544438355 && LODWORD(v14[1].Previous) )
      Previous = (int)v14[1].Previous;
  }
  LastError = GetLastError();
  _snprintf_s(
    Buffer,
    0x200u,
    0x1FFu,
    "%s(%d): Memory allocation failed in function %s\n   Expression: %s\n",
    v11,
    Previous,
    FrameName,
    byte_18008517D);
  Buffer[511] = 0;
  OutputDebugStringA(Buffer);
  SetLastError(LastError);
  SetLastError(0xEu);
  v6 = 0;
  *v22 = 0;
LABEL_5:
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v6 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v17 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v17, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v6;
}

```

## disassembly

```asm
0x180045460  mov     r11, rsp
0x180045463  push    rbx
0x180045464  sub     rsp, 2A0h
0x18004546b  mov     rax, cs:__security_cookie
0x180045472  xor     rax, rsp
0x180045475  mov     [rsp+2A8h+var_28], rax
0x18004547d  mov     [r11+18h], rsi
0x180045481  lea     rax, qword_180071390
0x180045488  mov     [r11+20h], rdi
0x18004548c  mov     rsi, rcx
0x18004548f  mov     [r11-10h], r14
0x180045493  lea     rcx, [rsp+2A8h+Frame]; Frame
0x180045498  mov     [rsp+2A8h+Frame.Context], rax
0x18004549d  xor     r14d, r14d
0x1800454a0  lea     rax, [rsp+2A8h+var_268]
0x1800454a5  mov     [rsp+2A8h+var_268], r14d
0x1800454aa  mov     ebx, 1
0x1800454af  mov     [rsp+2A8h+Frame.Previous], r14
0x1800454b4  mov     [rsp+2A8h+var_238], rax
0x1800454b9  mov     rdi, r9
0x1800454bc  mov     [rsp+2A8h+Frame.Flags], ebx
0x1800454c0  mov     [rsp+2A8h+var_248], 20737853h
0x1800454c9  mov     [rsp+2A8h+var_240], 2Eh ; '.'
0x1800454d1  call    cs:__imp_RtlPushFrame
0x1800454d8  nop     dword ptr [rax+rax+00h]
0x1800454dd  cmp     cs:g_FusionEnterExitTracingEnabled, r14b
0x1800454e4  jnz     loc_1800455A1
0x1800454ea  mov     rcx, cs:g_hHeap; hHeap
0x1800454f1  xor     edx, edx; dwFlags
0x1800454f3  mov     r8d, 38h ; '8'; dwBytes
0x1800454f9  call    cs:__imp_HeapAlloc
0x180045500  nop     dword ptr [rax+rax+00h]
0x180045505  test    rax, rax
0x180045508  jz      loc_1800455AB
0x18004550e  mov     rcx, [rsp+2A8h+arg_20]
0x180045516  mov     [rax+34h], r14b
0x18004551a  mov     [rax+18h], r14
0x18004551e  mov     [rax+20h], r14
0x180045522  mov     [rax+10h], r14d
0x180045526  mov     [rax+30h], r14d
0x18004552a  mov     [rax+8], rcx
0x18004552e  xor     ecx, ecx; dwErrCode
0x180045530  mov     [rax], rdi
0x180045533  mov     [rax+2Ch], bl
0x180045536  mov     [rax+28h], ebx
0x180045539  mov     [rsi], rax
0x18004553c  call    cs:__imp_SetLastError
0x180045543  nop     dword ptr [rax+rax+00h]
0x180045548  mov     rax, [rsp+2A8h+var_238]
0x18004554d  mov     [rax], ebx
0x18004554f  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180045556  mov     r14, [rsp+2A8h+var_10]
0x18004555e  mov     rdi, [rsp+2A8h+arg_18]
0x180045566  mov     rsi, [rsp+2A8h+arg_10]
0x18004556e  jnz     loc_1800456E7
0x180045574  lea     rcx, [rsp+2A8h+Frame]; Frame
0x180045579  call    cs:__imp_RtlPopFrame
0x180045580  nop     dword ptr [rax+rax+00h]
0x180045585  mov     eax, ebx
0x180045587  mov     rcx, [rsp+2A8h+var_28]
0x18004558f  xor     rcx, rsp; StackCookie
0x180045592  call    __security_check_cookie
0x180045597  add     rsp, 2A0h
0x18004559e  pop     rbx
0x18004559f  retn
0x1800455a1  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x1800455a6  jmp     loc_1800454EA
0x1800455ab  mov     [rsp+2A8h+arg_8], rbp
0x1800455b3  mov     edi, r14d
0x1800455b6  mov     [rsp+2A8h+var_18], r15
0x1800455be  lea     r15, byte_18008517D
0x1800455c5  mov     rsi, r15
0x1800455c8  mov     rbp, r15
0x1800455cb  call    cs:__imp_RtlGetFrame
0x1800455d2  nop     dword ptr [rax+rax+00h]
0x1800455d7  test    rax, rax
0x1800455da  jnz     loc_18004568E
0x1800455e0  mov     rcx, r14
0x1800455e3  test    rax, rax
0x1800455e6  jnz     loc_180045699
0x1800455ec  call    cs:__imp_GetLastError
0x1800455f3  nop     dword ptr [rax+rax+00h]
0x1800455f8  mov     [rsp+2A8h+var_270], r15
0x1800455fd  lea     r9, Format; "%s(%d): Memory allocation failed in fun"...
0x180045604  mov     [rsp+2A8h+var_278], rbp
0x180045609  lea     rcx, [rsp+2A8h+Buffer]; Buffer
0x180045611  mov     [rsp+2A8h+var_280], edi
0x180045615  mov     edx, 200h; BufferCount
0x18004561a  mov     r8d, 1FFh; MaxCount
0x180045620  mov     [rsp+2A8h+var_288], rsi
0x180045625  mov     ebx, eax
0x180045627  call    cs:__imp__snprintf_s
0x18004562e  nop     dword ptr [rax+rax+00h]
0x180045633  lea     rcx, [rsp+2A8h+Buffer]; lpOutputString
0x18004563b  mov     [rsp+2A8h+var_29], r14b
0x180045643  call    cs:__imp_OutputDebugStringA
0x18004564a  nop     dword ptr [rax+rax+00h]
0x18004564f  mov     ecx, ebx; dwErrCode
0x180045651  call    cs:__imp_SetLastError
0x180045658  nop     dword ptr [rax+rax+00h]
0x18004565d  mov     ecx, 0Eh; dwErrCode
0x180045662  call    cs:__imp_SetLastError
0x180045669  nop     dword ptr [rax+rax+00h]
0x18004566e  mov     rax, [rsp+2A8h+var_238]
0x180045673  mov     ebx, r14d
0x180045676  mov     r15, [rsp+2A8h+var_18]
0x18004567e  mov     rbp, [rsp+2A8h+arg_8]
0x180045686  mov     [rax], r14d
0x180045689  jmp     loc_18004554F
0x18004568e  test    [rax], bl
0x180045690  jz      loc_1800455E0
0x180045696  mov     rcx, rax
0x180045699  mov     rdx, [rax+10h]
0x18004569d  test    rdx, rdx
0x1800456a0  jz      short loc_1800456BE
0x1800456a2  mov     rax, [rdx+8]
0x1800456a6  test    rax, rax
0x1800456a9  jz      short loc_1800456AE
0x1800456ab  mov     rbp, rax
0x1800456ae  test    [rdx], bl
0x1800456b0  jz      short loc_1800456BE
0x1800456b2  mov     rax, [rdx+10h]
0x1800456b6  test    rax, rax
0x1800456b9  jz      short loc_1800456BE
0x1800456bb  mov     rsi, rax
0x1800456be  test    rcx, rcx
0x1800456c1  jz      loc_1800455EC
0x1800456c7  cmp     qword ptr [rcx+18h], 20737853h
0x1800456cf  jnz     loc_1800455EC
0x1800456d5  mov     eax, [rcx+20h]
0x1800456d8  test    eax, eax
0x1800456da  jz      loc_1800455EC
0x1800456e0  mov     edi, eax
0x1800456e2  jmp     loc_1800455EC
0x1800456e7  test    ebx, ebx
0x1800456e9  jz      short loc_1800456F7
0x1800456eb  xor     ecx, ecx; char *
0x1800456ed  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x1800456f2  jmp     loc_180045574
0x1800456f7  call    cs:__imp_GetLastError
0x1800456fe  nop     dword ptr [rax+rax+00h]
0x180045703  mov     ecx, eax; unsigned int
0x180045705  xor     edx, edx; Format
0x180045707  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18004570c  jmp     loc_180045574
```
