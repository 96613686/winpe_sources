# SmpAllocateControlBlock

- ea: `0x1400041d0`
- end: `0x1400045fb`
- name: `SmpAllocateControlBlock`
- size: `1067`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400036d0`

## callees

- `0x1400041d0`
- `0x140005998`
- `0x14000d4c0`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtClose` at `0x14000458a`
- `ntdll!NtClose` at `0x1400045f0`
- `ntdll!NtClose` at `0x14000458a`
- `ntdll!NtClose` at `0x1400045f0`
- `ntdll!RtlAllocateHeap` at `0x140004238`
- `ntdll!RtlAllocateHeap` at `0x140004238`
- `ntdll!RtlFreeHeap` at `0x1400045bd`
- `ntdll!RtlFreeHeap` at `0x1400045bd`
- `ntdll!NtCreateEvent` at `0x14000448c`
- `ntdll!NtCreateEvent` at `0x1400044af`
- `ntdll!NtCreateEvent` at `0x14000448c`
- `ntdll!NtCreateEvent` at `0x1400044af`
- `ntdll!NtCreateSection` at `0x1400043d2`
- `ntdll!NtCreateSection` at `0x1400043d2`
- `ntdll!NtMapViewOfSection` at `0x140004445`
- `ntdll!NtMapViewOfSection` at `0x140004445`
- `ntdll!NtUnmapViewOfSection` at `0x1400045e5`
- `ntdll!NtUnmapViewOfSection` at `0x1400045e5`

## pseudocode

```c
PVOID SmpAllocateControlBlock()
{
  PVOID Heap; // rbx
  __int64 v1; // rax
  const char *v2; // rcx
  __int64 v3; // r8
  _BYTE *v4; // rdx
  _BYTE *v5; // rax
  __int128 v6; // xmm1
  __int64 v7; // rcx
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  NTSTATUS v20; // eax
  void *v21; // r14
  NTSTATUS v22; // eax
  NTSTATUS v23; // r15d
  NTSTATUS v24; // eax
  PVOID result; // rax
  void *SectionHandle; // [rsp+50h] [rbp-B0h] BYREF
  PVOID BaseAddress; // [rsp+58h] [rbp-A8h] BYREF
  void *EventHandle; // [rsp+60h] [rbp-A0h] BYREF
  _LARGE_INTEGER MaximumSize; // [rsp+68h] [rbp-98h] BYREF
  void *v30; // [rsp+70h] [rbp-90h] BYREF
  ULONG_PTR ViewSize; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES v32; // [rsp+80h] [rbp-80h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v34[12]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v35; // [rsp+1A0h] [rbp+A0h]
  __int128 v36; // [rsp+1B0h] [rbp+B0h]

  MaximumSize.QuadPart = 0;
  memset(&ObjectAttributes, 0, 44);
  SectionHandle = 0;
  Heap = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), SmBaseTag + 0x80000, 0x80u);
  if ( !Heap )
  {
    memset_0(v34, 0, 0xE0u);
    v1 = 2147483646;
    LODWORD(v35) = -1073741670;
    v2 = "SmpAllocateControlBlock";
    DWORD2(v36) = 185;
    v3 = 64;
    v4 = v34;
    do
    {
      if ( !v1 )
        break;
      if ( !*v2 )
        break;
      *v4++ = *v2++;
      --v1;
      --v3;
    }
    while ( v3 );
    v5 = v4 - 1;
    if ( v3 )
      v5 = v4;
    *v5 = 0;
    v6 = v34[1];
    v7 = 224LL * (_InterlockedIncrement(&dword_14002EE94) % 16);
    *(_OWORD *)&SmpBlackboxBuffer[v7 + 8] = v34[0];
    v8 = v34[2];
    *(_OWORD *)&SmpBlackboxBuffer[v7 + 24] = v6;
    v9 = v34[3];
    *(_OWORD *)&SmpBlackboxBuffer[v7 + 40] = v8;
    v10 = v34[4];
    *(_OWORD *)&SmpBlackboxBuffer[v7 + 56] = v9;
    v11 = v34[5];
    *(_OWORD *)&SmpBlackboxBuffer[v7 + 72] = v10;
    v12 = v34[6];
    *(_OWORD *)&SmpBlackboxBuffer[v7 + 88] = v11;
    v13 = v34[7];
    *(_OWORD *)&SmpBlackboxBuffer[v7 + 104] = v12;
    v14 = v34[8];
    *(_OWORD *)&SmpBlackboxBuffer[v7 + 120] = v13;
    v15 = v34[9];
    *(_OWORD *)&SmpBlackboxBuffer[v7 + 136] = v14;
    v16 = v34[10];
    *(_OWORD *)&SmpBlackboxBuffer[v7 + 152] = v15;
    v17 = v34[11];
    *(_OWORD *)&SmpBlackboxBuffer[v7 + 168] = v16;
    v18 = v35;
    *(_OWORD *)&SmpBlackboxBuffer[v7 + 184] = v17;
    v19 = v36;
    *(_OWORD *)&SmpBlackboxBuffer[v7 + 200] = v18;
    *(_OWORD *)&SmpBlackboxBuffer[v7 + 216] = v19;
    goto LABEL_17;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Attributes = 2;
  ObjectAttributes.ObjectName = 0;
  MaximumSize.QuadPart = 24;
  v20 = NtCreateSection(&SectionHandle, 6u, &ObjectAttributes, &MaximumSize, 4u, 0x8400000u, 0);
  if ( v20 >= 0 )
  {
    v21 = SectionHandle;
    memset(&v32, 0, 44);
    v30 = 0;
    EventHandle = 0;
    BaseAddress = 0;
    ViewSize = 0;
    v22 = NtMapViewOfSection(
            SectionHandle,
            (HANDLE)0xFFFFFFFFFFFFFFFFLL,
            &BaseAddress,
            0,
            0,
            0,
            &ViewSize,
            ViewUnmap,
            0,
            4u);
    if ( v22 < 0 )
    {
      SmpLogFailure("SmpInitializeControlBlock", 292, (unsigned int)v22);
      BaseAddress = 0;
    }
    else
    {
      v32.Length = 48;
      v32.RootDirectory = 0;
      v32.Attributes = 2;
      v32.ObjectName = 0;
      *(_OWORD *)&v32.SecurityDescriptor = 0;
      v23 = NtCreateEvent(&EventHandle, 0x1F0003u, &v32, SynchronizationEvent, 0);
      if ( v23 < 0 )
      {
        memset_0(v34, 0, 0xE0u);
        SmpInternalLogFailure("SmpInitializeControlBlock", 311, (unsigned int)v23, v34);
        EventHandle = 0;
LABEL_15:
        if ( BaseAddress )
          NtUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
LABEL_17:
        if ( SectionHandle )
          NtClose(SectionHandle);
        if ( !Heap )
          return 0;
        goto LABEL_25;
      }
      v24 = NtCreateEvent(&v30, 0x1F0003u, &v32, SynchronizationEvent, 0);
      if ( v24 >= 0 )
      {
        memset_0(Heap, 0, 0x80u);
        *((_QWORD *)Heap + 2) = BaseAddress;
        *((_QWORD *)Heap + 4) = EventHandle;
        *((_QWORD *)Heap + 5) = v30;
        result = Heap;
        *((_QWORD *)Heap + 3) = v21;
        *((_DWORD *)Heap + 1) = 1;
        return result;
      }
      SmpLogFailure("SmpInitializeControlBlock", 325, (unsigned int)v24);
    }
    if ( EventHandle )
      NtClose(EventHandle);
    goto LABEL_15;
  }
  SmpLogFailure("SmpAllocateControlBlock", 206, (unsigned int)v20);
  SectionHandle = 0;
LABEL_25:
  RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Heap);
  return 0;
}

```

## disassembly

```asm
0x1400041d0  push    rbp
0x1400041d2  push    rbx
0x1400041d3  push    rsi
0x1400041d4  push    rdi
0x1400041d5  push    r12
0x1400041d7  push    r14
0x1400041d9  push    r15
0x1400041db  lea     rbp, [rsp-0D0h]
0x1400041e3  sub     rsp, 1D0h
0x1400041ea  mov     rax, cs:__security_cookie
0x1400041f1  xor     rax, rsp
0x1400041f4  mov     [rbp+100h+var_40], rax
0x1400041fb  mov     edx, cs:SmBaseTag
0x140004201  xorps   xmm0, xmm0
0x140004204  movups  xmmword ptr [rbp+100h+ObjectAttributes.ObjectName], xmm0
0x140004208  xor     r12d, r12d
0x14000420b  xor     eax, eax
0x14000420d  movups  xmmword ptr [rbp+100h+ObjectAttributes+1Ch], xmm0
0x140004211  mov     qword ptr [rsp+200h+MaximumSize], r12
0x140004216  add     edx, 80000h; Flags
0x14000421c  movups  xmmword ptr [rbp+100h+ObjectAttributes.Length], xmm0
0x140004220  mov     [rsp+200h+SectionHandle], r12
0x140004225  mov     r8d, 80h; Size
0x14000422b  mov     rcx, gs:60h
0x140004234  mov     rcx, [rcx+30h]; HeapHandle
0x140004238  call    cs:__imp_RtlAllocateHeap
0x14000423e  mov     rbx, rax
0x140004241  test    rax, rax
0x140004244  jnz     loc_140004383
0x14000424a  xor     edx, edx; Val
0x14000424c  lea     rcx, [rbp+100h+var_120]; void *
0x140004250  mov     r8d, 0E0h; Size
0x140004256  call    memset_0
0x14000425b  mov     eax, 7FFFFFFEh
0x140004260  mov     dword ptr [rbp+100h+var_60], 0C000009Ah
0x14000426a  lea     rcx, aSmpallocatecon; "SmpAllocateControlBlock"
0x140004271  mov     [rbp+100h+var_48], 0B9h
0x14000427b  mov     r8d, 40h ; '@'
0x140004281  lea     rdx, [rbp+100h+var_120]
0x140004285  test    rax, rax
0x140004288  jz      short loc_1400042A5
0x14000428a  movzx   r9d, byte ptr [rcx]
0x14000428e  test    r9b, r9b
0x140004291  jz      short loc_1400042A5
0x140004293  mov     [rdx], r9b
0x140004296  inc     rcx
0x140004299  inc     rdx
0x14000429c  dec     rax
0x14000429f  sub     r8, 1
0x1400042a3  jnz     short loc_140004285
0x1400042a5  test    r8, r8
0x1400042a8  lea     rax, [rdx-1]
0x1400042ac  mov     edi, 1
0x1400042b1  cmovnz  rax, rdx
0x1400042b5  mov     [rax], r12b
0x1400042b8  lock xadd cs:dword_14002EE94, edi
0x1400042c0  inc     edi
0x1400042c2  and     edi, 8000000Fh
0x1400042c8  jge     short loc_1400042D1
0x1400042ca  dec     edi
0x1400042cc  or      edi, 0FFFFFFF0h
0x1400042cf  inc     edi
0x1400042d1  movaps  xmm0, [rbp+100h+var_120]
0x1400042d5  movaps  xmm1, [rbp+100h+var_110]
0x1400042d9  movsxd  rax, edi
0x1400042dc  imul    rcx, rax, 0E0h
0x1400042e3  lea     rax, SmpBlackboxBuffer
0x1400042ea  movups  xmmword ptr [rcx+rax+8], xmm0
0x1400042ef  movaps  xmm0, [rbp+100h+var_100]
0x1400042f3  movups  xmmword ptr [rcx+rax+18h], xmm1
0x1400042f8  movaps  xmm1, [rbp+100h+var_F0]
0x1400042fc  movups  xmmword ptr [rcx+rax+28h], xmm0
0x140004301  movaps  xmm0, [rbp+100h+var_E0]
0x140004305  movups  xmmword ptr [rcx+rax+38h], xmm1
0x14000430a  movaps  xmm1, [rbp+100h+var_D0]
0x14000430e  movups  xmmword ptr [rcx+rax+48h], xmm0
0x140004313  movaps  xmm0, [rbp+100h+var_C0]
0x140004317  movups  xmmword ptr [rcx+rax+58h], xmm1
0x14000431c  movaps  xmm1, [rbp+100h+var_B0]
0x140004320  movups  xmmword ptr [rcx+rax+68h], xmm0
0x140004325  movaps  xmm0, [rbp+100h+var_A0]
0x140004329  movups  xmmword ptr [rcx+rax+78h], xmm1
0x14000432e  movaps  xmm1, [rbp+100h+var_90]
0x140004332  movups  xmmword ptr [rcx+rax+88h], xmm0
0x14000433a  movaps  xmm0, [rbp+100h+var_80]
0x140004341  movups  xmmword ptr [rcx+rax+98h], xmm1
0x140004349  movaps  xmm1, [rbp+100h+var_70]
0x140004350  movups  xmmword ptr [rcx+rax+0A8h], xmm0
0x140004358  movaps  xmm0, [rbp+100h+var_60]
0x14000435f  movups  xmmword ptr [rcx+rax+0B8h], xmm1
0x140004367  movaps  xmm1, xmmword ptr [rbp+0B0h]
0x14000436e  movups  xmmword ptr [rcx+rax+0C8h], xmm0
0x140004376  movups  xmmword ptr [rcx+rax+0D8h], xmm1
0x14000437e  jmp     loc_140004530
0x140004383  xorps   xmm0, xmm0
0x140004386  mov     [rsp+200h+FileHandle], r12; FileHandle
0x14000438b  mov     [rsp+200h+AllocationAttributes], 8400000h; AllocationAttributes
0x140004393  lea     r9, [rsp+200h+MaximumSize]; MaximumSize
0x140004398  lea     r8, [rbp+100h+ObjectAttributes]; ObjectAttributes
0x14000439c  mov     [rsp+200h+SectionPageProtection], 4; SectionPageProtection
0x1400043a4  mov     edx, 6; DesiredAccess
0x1400043a9  mov     [rbp+100h+ObjectAttributes.Length], 30h ; '0'
0x1400043b0  lea     rcx, [rsp+200h+SectionHandle]; SectionHandle
0x1400043b5  mov     [rbp+100h+ObjectAttributes.RootDirectory], r12
0x1400043b9  movdqu  xmmword ptr [rbp+100h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400043be  mov     [rbp+100h+ObjectAttributes.Attributes], 2
0x1400043c5  mov     [rbp+100h+ObjectAttributes.ObjectName], r12
0x1400043c9  mov     qword ptr [rsp+200h+MaximumSize], 18h
0x1400043d2  call    cs:__imp_NtCreateSection
0x1400043d8  test    eax, eax
0x1400043da  js      loc_140004592
0x1400043e0  mov     r14, [rsp+200h+SectionHandle]
0x1400043e5  lea     r8, [rsp+200h+BaseAddress]; BaseAddress
0x1400043ea  mov     [rsp+200h+AccessProtection], 4; AccessProtection
0x1400043f2  xorps   xmm0, xmm0
0x1400043f5  mov     [rsp+200h+AllocationType], r12d; AllocationType
0x1400043fa  xor     eax, eax
0x1400043fc  mov     [rsp+200h+InheritDisposition], 2; InheritDisposition
0x140004404  lea     rax, [rsp+200h+ViewSize]
0x140004409  mov     [rsp+200h+FileHandle], rax; ViewSize
0x14000440e  xor     r9d, r9d; ZeroBits
0x140004411  movups  xmmword ptr [rbp+100h+var_180.ObjectName], xmm0
0x140004415  mov     qword ptr [rsp+200h+AllocationAttributes], r12; SectionOffset
0x14000441a  mov     rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140004421  mov     rcx, r14; SectionHandle
0x140004424  mov     qword ptr [rsp+200h+SectionPageProtection], r12; CommitSize
0x140004429  movups  xmmword ptr [rbp+100h+var_180.Length], xmm0
0x14000442d  mov     [rsp+200h+var_190], r12
0x140004432  movups  xmmword ptr [rbp+100h+var_180+1Ch], xmm0
0x140004436  mov     [rsp+200h+EventHandle], r12
0x14000443b  mov     [rsp+200h+BaseAddress], r12
0x140004440  mov     [rsp+200h+ViewSize], r12
0x140004445  call    cs:__imp_NtMapViewOfSection
0x14000444b  test    eax, eax
0x14000444d  js      loc_140004567
0x140004453  xorps   xmm0, xmm0
0x140004456  mov     [rbp+100h+var_180.Length], 30h ; '0'
0x14000445d  mov     edi, 1
0x140004462  mov     [rbp+100h+var_180.RootDirectory], r12
0x140004466  mov     r9d, edi; EventType
0x140004469  mov     [rbp+100h+var_180.Attributes], 2
0x140004470  lea     r8, [rbp+100h+var_180]; ObjectAttributes
0x140004474  mov     [rbp+100h+var_180.ObjectName], r12
0x140004478  mov     edx, 1F0003h; DesiredAccess
0x14000447d  mov     byte ptr [rsp+200h+SectionPageProtection], r12b; InitialState
0x140004482  lea     rcx, [rsp+200h+EventHandle]; EventHandle
0x140004487  movdqu  xmmword ptr [rbp+100h+var_180.SecurityDescriptor], xmm0
0x14000448c  call    cs:__imp_NtCreateEvent
0x140004492  mov     r15d, eax
0x140004495  test    eax, eax
0x140004497  js      short loc_1400044F4
0x140004499  mov     r9d, edi; EventType
0x14000449c  mov     byte ptr [rsp+200h+SectionPageProtection], r12b; InitialState
0x1400044a1  lea     r8, [rbp+100h+var_180]; ObjectAttributes
0x1400044a5  mov     edx, 1F0003h; DesiredAccess
0x1400044aa  lea     rcx, [rsp+200h+var_190]; EventHandle
0x1400044af  call    cs:__imp_NtCreateEvent
0x1400044b5  test    eax, eax
0x1400044b7  js      loc_1400045C8
0x1400044bd  xor     edx, edx; Val
0x1400044bf  mov     r8d, 80h; Size
0x1400044c5  mov     rcx, rbx; void *
0x1400044c8  call    memset_0
0x1400044cd  mov     rax, [rsp+200h+BaseAddress]
0x1400044d2  mov     [rbx+10h], rax
0x1400044d6  mov     rax, [rsp+200h+EventHandle]
0x1400044db  mov     [rbx+20h], rax
0x1400044df  mov     rax, [rsp+200h+var_190]
0x1400044e4  mov     [rbx+28h], rax
0x1400044e8  mov     rax, rbx
0x1400044eb  mov     [rbx+18h], r14
0x1400044ef  mov     [rbx+4], edi
0x1400044f2  jmp     short loc_140004546
0x1400044f4  xor     edx, edx; Val
0x1400044f6  lea     rcx, [rbp+100h+var_120]; void *
0x1400044fa  mov     r8d, 0E0h; Size
0x140004500  call    memset_0
0x140004505  lea     r9, [rbp+100h+var_120]
0x140004509  mov     r8d, r15d
0x14000450c  mov     edx, 137h
0x140004511  lea     rcx, aSmpinitializec; "SmpInitializeControlBlock"
0x140004518  call    SmpInternalLogFailure
0x14000451d  mov     [rsp+200h+EventHandle], r12
0x140004522  mov     rdx, [rsp+200h+BaseAddress]; BaseAddress
0x140004527  test    rdx, rdx
0x14000452a  jnz     loc_1400045DE
0x140004530  mov     rcx, [rsp+200h+SectionHandle]; Handle
0x140004535  test    rcx, rcx
0x140004538  jnz     loc_1400045F0
0x14000453e  test    rbx, rbx
0x140004541  jnz     short loc_1400045AB
0x140004543  mov     rax, r12
0x140004546  mov     rcx, [rbp+100h+var_40]
0x14000454d  xor     rcx, rsp; StackCookie
0x140004550  call    __security_check_cookie
0x140004555  add     rsp, 1D0h
0x14000455c  pop     r15
0x14000455e  pop     r14
0x140004560  pop     r12
0x140004562  pop     rdi
0x140004563  pop     rsi
0x140004564  pop     rbx
0x140004565  pop     rbp
0x140004566  retn
0x140004567  mov     r8d, eax
0x14000456a  lea     rcx, aSmpinitializec; "SmpInitializeControlBlock"
0x140004571  mov     edx, 124h
0x140004576  call    SmpLogFailure
0x14000457b  mov     [rsp+200h+BaseAddress], r12
0x140004580  mov     rcx, [rsp+200h+EventHandle]; Handle
0x140004585  test    rcx, rcx
0x140004588  jz      short loc_140004522
0x14000458a  call    cs:__imp_NtClose
0x140004590  jmp     short loc_140004522
0x140004592  mov     r8d, eax
0x140004595  lea     rcx, aSmpallocatecon; "SmpAllocateControlBlock"
0x14000459c  mov     edx, 0CEh
0x1400045a1  call    SmpLogFailure
0x1400045a6  mov     [rsp+200h+SectionHandle], r12
0x1400045ab  mov     rcx, gs:60h
0x1400045b4  mov     r8, rbx; BaseAddress
0x1400045b7  xor     edx, edx; Flags
0x1400045b9  mov     rcx, [rcx+30h]; HeapHandle
0x1400045bd  call    cs:__imp_RtlFreeHeap
0x1400045c3  jmp     loc_140004543
0x1400045c8  mov     r8d, eax
0x1400045cb  lea     rcx, aSmpinitializec; "SmpInitializeControlBlock"
0x1400045d2  mov     edx, 145h
0x1400045d7  call    SmpLogFailure
0x1400045dc  jmp     short loc_140004580
0x1400045de  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400045e5  call    cs:__imp_NtUnmapViewOfSection
0x1400045eb  jmp     loc_140004530
0x1400045f0  call    cs:__imp_NtClose
0x1400045f6  jmp     loc_14000453E
```
