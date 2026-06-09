# BeginTracing(ushort const *,ushort const *,_GUID const *,ulong,unsigned __int64 *)

- ea: `0x14001181c`
- end: `0x140011b01`
- name: `?BeginTracing@@YAJPEBG0PEBU_GUID@@KPEA_K@Z`
- size: `741`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, unsigned int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140011b08`

## callees

- `0x140001258`
- `0x140001264`
- `0x140001a63`
- `0x1400044e0`
- `0x14001181c`
- `0x140013490`
- `0x140014910`

## import_xrefs

- `ADVAPI32!StartTraceW` at `0x140011a1e`
- `ADVAPI32!StartTraceW` at `0x140011a1e`
- `ADVAPI32!EnableTrace` at `0x140011a78`
- `ADVAPI32!EnableTrace` at `0x140011a78`
- `ADVAPI32!ControlTraceW` at `0x140011acb`
- `ADVAPI32!ControlTraceW` at `0x140011acb`
- `ADVAPI32!CloseTrace` at `0x140011ad6`
- `ADVAPI32!CloseTrace` at `0x140011ad6`
- `KERNEL32!GetCurrentProcessId` at `0x140011878`
- `KERNEL32!GetCurrentProcessId` at `0x140011878`

## string_xrefs

- `0x1400119e7`: `Failed to copy log file name`

## pseudocode

```c
__int64 __fastcall BeginTracing(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        ULONG a4,
        unsigned __int64 *a5)
{
  signed int v8; // ebx
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rcx
  size_t v12; // r14
  struct _EVENT_TRACE_PROPERTIES *v13; // rax
  struct _EVENT_TRACE_PROPERTIES *v14; // rdi
  __int64 v15; // rax
  GUID v16; // xmm0
  ULONG v17; // eax
  unsigned __int64 v18; // rdx
  _WORD *v19; // r8
  __int64 v20; // rax
  _WORD *v21; // rcx
  signed int v22; // eax
  ULONG started; // eax
  signed int v24; // esi
  DWORD CurrentProcessId; // [rsp+20h] [rbp-E0h]
  ULONG64 TraceHandle; // [rsp+30h] [rbp-D0h] BYREF
  ULONG EnableLevel; // [rsp+38h] [rbp-C8h]
  WCHAR InstanceName[512]; // [rsp+40h] [rbp-C0h] BYREF

  EnableLevel = a4;
  TraceHandle = 0;
  memset_0(InstanceName, 0, sizeof(InstanceName));
  CurrentProcessId = GetCurrentProcessId();
  v8 = StringCchPrintfW(InstanceName, 0x200u, L"%s%ld", a2, CurrentProcessId);
  if ( v8 < 0 )
  {
    WusaLogDebugEventA(L"BeginTracing", 59, "Failed creating the tracing session name");
    goto LABEL_38;
  }
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( InstanceName[v10] );
  v11 = -1;
  do
    ++v11;
  while ( a1[v11] );
  v12 = (unsigned int)(2 * (v11 + v10) + 124);
  v13 = (struct _EVENT_TRACE_PROPERTIES *)operator new((unsigned int)v12);
  v14 = v13;
  if ( !v13 )
  {
    WusaLogDebugEventA(L"BeginTracing", 66, "Failed to allocate memory for event trace properties");
    v8 = -2147024882;
    goto LABEL_38;
  }
  memset_0(v13, 0, v12);
  v14->Wnode.BufferSize = v12;
  v14->Wnode.Flags = 0x20000;
  v15 = -1;
  v14->Wnode.ClientContext = 1;
  v16 = *a3;
  v14->LogFileMode = 16777220;
  v14->LoggerNameOffset = 120;
  v14->Wnode.Guid = v16;
  do
    ++v15;
  while ( InstanceName[v15] );
  v17 = 2 * v15 + 122;
  v14->LogFileNameOffset = v17;
  do
    ++v9;
  while ( a1[v9] );
  v18 = v9 + 1;
  v19 = (_WORD *)((char *)v14 + v17);
  v8 = -2147024809;
  if ( v18 )
  {
    if ( v18 > 0x7FFFFFFF )
    {
      *v19 = 0;
      goto LABEL_23;
    }
    v20 = 2147483646;
    do
    {
      if ( !v20 )
        break;
      if ( !*a1 )
        break;
      *v19++ = *a1++;
      --v20;
      --v18;
    }
    while ( v18 );
    v21 = v19 - 1;
    if ( v18 )
      v21 = v19;
    v22 = v18 == 0 ? 0x8007007A : 0;
    *v21 = 0;
  }
  else
  {
    v22 = -2147024809;
  }
  v8 = v22;
  if ( v22 >= 0 )
  {
    started = StartTraceW(&TraceHandle, InstanceName, v14);
    v24 = started;
    if ( started == 183 || started == 32 )
    {
      *a5 = 0;
      v8 = 0;
      goto LABEL_37;
    }
    if ( started )
    {
      WusaLogDebugEventA(L"BeginTracing", 87, "Start trace failed");
    }
    else
    {
      v24 = EnableTrace(1u, 0, EnableLevel, a3, TraceHandle);
      if ( !v24 )
      {
        *a5 = TraceHandle;
        TraceHandle = 0;
        goto LABEL_37;
      }
      WusaLogDebugEventA(L"BeginTracing", 90, "Enable trace failed");
    }
    if ( v24 > 0 )
      v8 = (unsigned __int16)v24 | 0x80070000;
    else
      v8 = v24;
    goto LABEL_37;
  }
LABEL_23:
  WusaLogDebugEventA(L"BeginTracing", 77, "Failed to copy log file name");
LABEL_37:
  operator delete(v14);
LABEL_38:
  if ( TraceHandle )
  {
    ControlTraceW(0, InstanceName, 0, 1u);
    CloseTrace(TraceHandle);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14001181c  push    rbp
0x14001181e  push    rbx
0x14001181f  push    rsi
0x140011820  push    rdi
0x140011821  push    r12
0x140011823  push    r13
0x140011825  push    r14
0x140011827  push    r15
0x140011829  lea     rbp, [rsp-358h]
0x140011831  sub     rsp, 458h
0x140011838  mov     rax, cs:__security_cookie
0x14001183f  xor     rax, rsp
0x140011842  mov     [rbp+390h+var_50], rax
0x140011849  mov     r12, [rbp+390h+arg_20]
0x140011850  mov     r13, r8
0x140011853  mov     rbx, rdx
0x140011856  mov     [rsp+490h+EnableLevel], r9d
0x14001185b  mov     rsi, rcx
0x14001185e  xor     r14d, r14d
0x140011861  xor     edx, edx; Val
0x140011863  mov     [rsp+490h+TraceHandle], r14
0x140011868  mov     r8d, 400h; Size
0x14001186e  lea     rcx, [rsp+490h+InstanceName]; void *
0x140011873  call    memset_0
0x140011878  call    cs:__imp_GetCurrentProcessId
0x14001187e  mov     r9, rbx
0x140011881  lea     r8, aSLd; "%s%ld"
0x140011888  lea     rcx, [rsp+490h+InstanceName]; unsigned __int16 *
0x14001188d  mov     [rsp+490h+var_470], eax
0x140011891  mov     edx, 200h; unsigned __int64
0x140011896  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001189b  mov     ebx, eax
0x14001189d  test    eax, eax
0x14001189f  jns     short loc_1400118C0
0x1400118a1  lea     r8, aFailedCreating; "Failed creating the tracing session nam"...
0x1400118a8  mov     edi, r14d
0x1400118ab  lea     edx, [r14+3Bh]
0x1400118af  lea     rcx, aBegintracing; "BeginTracing"
0x1400118b6  call    WusaLogDebugEventA
0x1400118bb  jmp     loc_140011AB4
0x1400118c0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400118c4  lea     rcx, [rsp+490h+InstanceName]
0x1400118c9  mov     rax, rbx
0x1400118cc  inc     rax
0x1400118cf  cmp     [rcx+rax*2], r14w
0x1400118d4  jnz     short loc_1400118CC
0x1400118d6  mov     rcx, rbx
0x1400118d9  inc     rcx
0x1400118dc  cmp     [rsi+rcx*2], r14w
0x1400118e1  jnz     short loc_1400118D9
0x1400118e3  add     eax, ecx
0x1400118e5  lea     r14d, ds:7Ch[rax*2]
0x1400118ed  mov     ecx, r14d; Size
0x1400118f0  mov     r15d, r14d
0x1400118f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400118f8  mov     rdi, rax
0x1400118fb  test    rax, rax
0x1400118fe  jnz     short loc_140011923
0x140011900  lea     r8, aFailedToAlloca_20; "Failed to allocate memory for event tra"...
0x140011907  lea     edx, [rax+42h]
0x14001190a  lea     rcx, aBegintracing; "BeginTracing"
0x140011911  call    WusaLogDebugEventA
0x140011916  xor     r14d, r14d
0x140011919  mov     ebx, 8007000Eh
0x14001191e  jmp     loc_140011AB4
0x140011923  mov     r8, r15; Size
0x140011926  xor     edx, edx; Val
0x140011928  mov     rcx, rdi; void *
0x14001192b  call    memset_0
0x140011930  mov     [rdi], r14d
0x140011933  lea     rcx, [rsp+490h+InstanceName]
0x140011938  mov     dword ptr [rdi+2Ch], 20000h
0x14001193f  mov     rax, rbx
0x140011942  mov     dword ptr [rdi+28h], 1
0x140011949  xor     r14d, r14d
0x14001194c  movups  xmm0, xmmword ptr [r13+0]
0x140011951  mov     dword ptr [rdi+40h], 1000004h
0x140011958  mov     dword ptr [rdi+74h], 78h ; 'x'
0x14001195f  movdqu  xmmword ptr [rdi+18h], xmm0
0x140011964  inc     rax
0x140011967  cmp     [rcx+rax*2], r14w
0x14001196c  jnz     short loc_140011964
0x14001196e  lea     eax, ds:7Ah[rax*2]
0x140011975  mov     [rdi+70h], eax
0x140011978  inc     rbx
0x14001197b  cmp     [rsi+rbx*2], r14w
0x140011980  jnz     short loc_140011978
0x140011982  lea     rdx, [rbx+1]
0x140011986  mov     r8d, eax
0x140011989  add     r8, rdi
0x14001198c  mov     ebx, 80070057h
0x140011991  test    rdx, rdx
0x140011994  jz      short loc_140011A04
0x140011996  cmp     rdx, 7FFFFFFFh
0x14001199d  ja      short loc_140011A0B
0x14001199f  mov     eax, 7FFFFFFEh
0x1400119a4  test    rax, rax
0x1400119a7  jz      short loc_1400119C6
0x1400119a9  movzx   ecx, word ptr [rsi]
0x1400119ac  test    cx, cx
0x1400119af  jz      short loc_1400119C6
0x1400119b1  mov     [r8], cx
0x1400119b5  add     rsi, 2
0x1400119b9  add     r8, 2
0x1400119bd  dec     rax
0x1400119c0  sub     rdx, 1
0x1400119c4  jnz     short loc_1400119A4
0x1400119c6  test    rdx, rdx
0x1400119c9  lea     rcx, [r8-2]
0x1400119cd  cmovnz  rcx, r8
0x1400119d1  neg     rdx
0x1400119d4  sbb     eax, eax
0x1400119d6  not     eax
0x1400119d8  and     eax, 8007007Ah
0x1400119dd  mov     [rcx], r14w
0x1400119e1  mov     ebx, eax
0x1400119e3  test    eax, eax
0x1400119e5  jns     short loc_140011A11
0x1400119e7  lea     r8, aFailedToCopyLo; "Failed to copy log file name"
0x1400119ee  mov     edx, 4Dh ; 'M'
0x1400119f3  lea     rcx, aBegintracing; "BeginTracing"
0x1400119fa  call    WusaLogDebugEventA
0x1400119ff  jmp     loc_140011AA9
0x140011a04  mov     eax, ebx
0x140011a06  test    rdx, rdx
0x140011a09  jz      short loc_1400119E1
0x140011a0b  mov     [r8], r14w
0x140011a0f  jmp     short loc_1400119E7
0x140011a11  mov     r8, rdi; Properties
0x140011a14  lea     rdx, [rsp+490h+InstanceName]; InstanceName
0x140011a19  lea     rcx, [rsp+490h+TraceHandle]; TraceHandle
0x140011a1e  call    cs:__imp_StartTraceW
0x140011a24  mov     esi, eax
0x140011a26  cmp     eax, 0B7h
0x140011a2b  jz      short loc_140011AA2
0x140011a2d  cmp     eax, 20h ; ' '
0x140011a30  jz      short loc_140011AA2
0x140011a32  test    eax, eax
0x140011a34  jz      short loc_140011A61
0x140011a36  lea     r8, aStartTraceFail; "Start trace failed"
0x140011a3d  mov     edx, 57h ; 'W'
0x140011a42  lea     rcx, aBegintracing; "BeginTracing"
0x140011a49  call    WusaLogDebugEventA
0x140011a4e  test    esi, esi
0x140011a50  jg      short loc_140011A56
0x140011a52  mov     ebx, esi
0x140011a54  jmp     short loc_140011AA9
0x140011a56  movzx   ebx, si
0x140011a59  or      ebx, 80070000h
0x140011a5f  jmp     short loc_140011AA9
0x140011a61  mov     rax, [rsp+490h+TraceHandle]
0x140011a66  xor     edx, edx; EnableFlag
0x140011a68  mov     r8d, [rsp+490h+EnableLevel]; EnableLevel
0x140011a6d  mov     r9, r13; ControlGuid
0x140011a70  mov     qword ptr [rsp+490h+var_470], rax; TraceHandle
0x140011a75  lea     ecx, [rdx+1]; Enable
0x140011a78  call    cs:__imp_EnableTrace
0x140011a7e  mov     esi, eax
0x140011a80  test    eax, eax
0x140011a82  jz      short loc_140011A92
0x140011a84  lea     r8, aEnableTraceFai; "Enable trace failed"
0x140011a8b  mov     edx, 5Ah ; 'Z'
0x140011a90  jmp     short loc_140011A42
0x140011a92  mov     rax, [rsp+490h+TraceHandle]
0x140011a97  mov     [r12], rax
0x140011a9b  mov     [rsp+490h+TraceHandle], r14
0x140011aa0  jmp     short loc_140011AA9
0x140011aa2  mov     [r12], r14
0x140011aa6  mov     ebx, r14d
0x140011aa9  mov     rcx, rdi; Block
0x140011aac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140011ab1  mov     rdi, r14
0x140011ab4  cmp     [rsp+490h+TraceHandle], r14
0x140011ab9  jz      short loc_140011ADC
0x140011abb  mov     r9d, 1; ControlCode
0x140011ac1  lea     rdx, [rsp+490h+InstanceName]; InstanceName
0x140011ac6  mov     r8, rdi; Properties
0x140011ac9  xor     ecx, ecx; TraceHandle
0x140011acb  call    cs:__imp_ControlTraceW
0x140011ad1  mov     rcx, [rsp+490h+TraceHandle]; TraceHandle
0x140011ad6  call    cs:__imp_CloseTrace
0x140011adc  mov     eax, ebx
0x140011ade  mov     rcx, [rbp+390h+var_50]
0x140011ae5  xor     rcx, rsp; StackCookie
0x140011ae8  call    __security_check_cookie
0x140011aed  add     rsp, 458h
0x140011af4  pop     r15
0x140011af6  pop     r14
0x140011af8  pop     r13
0x140011afa  pop     r12
0x140011afc  pop     rdi
0x140011afd  pop     rsi
0x140011afe  pop     rbx
0x140011aff  pop     rbp
0x140011b00  retn
```
