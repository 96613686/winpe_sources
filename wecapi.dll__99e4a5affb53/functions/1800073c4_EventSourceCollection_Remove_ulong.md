# EventSourceCollection::Remove(ulong)

- ea: `0x1800073c4`
- end: `0x1800075d7`
- name: `?Remove@EventSourceCollection@@QEAAXK@Z`
- size: `531`
- prototype: `void __fastcall(EventSourceCollection *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180005720`

## callees

- `0x180001aac`
- `0x1800025d0`
- `0x1800027ac`
- `0x180002900`
- `0x1800073c4`
- `0x18000996c`
- `0x18000d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall EventSourceCollection::Remove(EventSourceCollection *this, __int64 a2)
{
  unsigned __int64 v2; // rdi
  EventSourceCollection *v3; // rcx
  __int64 v4; // rsi
  __int64 v5; // rbx
  unsigned __int64 v6; // r10
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // r9
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  _BYTE pExceptionObject[64]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v13; // [rsp+70h] [rbp+8h] BYREF

  v2 = (unsigned int)a2;
  v13 = 0;
  GetClassifiedObject<Subscription>(*((_QWORD *)this + 3), a2, &v13);
  v4 = v13;
  if ( (*(_BYTE *)(v13 + 88) & 2) == 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 4317);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)pExceptionObject,
      0x10DDu,
      "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
      761);
    throw (wmi::GenericException *)pExceptionObject;
  }
  v5 = *(_QWORD *)(*(_QWORD *)(v13 + 40) + 8LL);
  EventSourceCollection::Validate(v3, (struct SubscriptionWriteData *)(v13 + 40), 0);
  if ( (unsigned int)v2 >= *(_DWORD *)(v5 + 56) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)pExceptionObject,
      0x57u,
      "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
      774);
    throw (wmi::GenericException *)pExceptionObject;
  }
  v6 = *(unsigned int *)(v5 + 80);
  v7 = (unsigned int)v2;
  if ( v2 < v6 )
  {
    do
    {
      v8 = (unsigned int)(v7 + 1);
      *(_DWORD *)(*(_QWORD *)(v5 + 40) + 4 * v7) = *(_DWORD *)(*(_QWORD *)(v5 + 40) + 4 * v8);
      v7 = v8;
    }
    while ( v8 < v6 );
    v9 = v2;
    do
    {
      *(_BYTE *)(v9 + *(_QWORD *)(v5 + 88)) = *(_BYTE *)(*(_QWORD *)(v5 + 88) + v9 + 1);
      ++v9;
    }
    while ( v9 < v6 );
    v10 = v2;
    do
    {
      *(_QWORD *)(*(_QWORD *)(v5 + 64) + 8LL * v10) = *(_QWORD *)(*(_QWORD *)(v5 + 64) + 8LL * (v10 + 1));
      ++v10;
    }
    while ( v10 < v6 );
    v11 = v2;
    do
    {
      *(_QWORD *)(*(_QWORD *)(v5 + 112) + 8LL * v11) = *(_QWORD *)(*(_QWORD *)(v5 + 112) + 8LL * (v11 + 1));
      ++v11;
    }
    while ( v11 < v6 );
    do
    {
      *(_QWORD *)(*(_QWORD *)(v5 + 136) + 8LL * (unsigned int)v2) = *(_QWORD *)(*(_QWORD *)(v5 + 136)
                                                                              + 8LL * (unsigned int)(v2 + 1));
      LODWORD(v2) = v2 + 1;
    }
    while ( (unsigned int)v2 < v6 );
  }
  --*(_DWORD *)(v5 + 32);
  --*(_DWORD *)(v5 + 80);
  --*(_DWORD *)(v5 + 56);
  --*(_DWORD *)(v5 + 104);
  --*(_DWORD *)(v5 + 128);
  *(_DWORD *)(v5 + 52) |= 1u;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 8), 0xFFFFFFFF) == 1 )
  {
    if ( v4 )
      (**(void (__fastcall ***)(__int64, __int64))v4)(v4, 1);
  }
}

```

## disassembly

```asm
0x1800073c4  mov     rax, rsp
0x1800073c7  mov     [rax+10h], rbx
0x1800073cb  mov     [rax+18h], rsi
0x1800073cf  push    rdi
0x1800073d0  sub     rsp, 60h
0x1800073d4  mov     edi, edx
0x1800073d6  mov     qword ptr [rax+8], 0
0x1800073de  lea     r8, [rax+8]
0x1800073e2  mov     rcx, [rcx+18h]
0x1800073e6  call    ??$GetClassifiedObject@VSubscription@@@@YAXPEAXW4ObjectType@@AEAV?$AutoRef@VSubscription@@@wmi@@@Z; GetClassifiedObject<Subscription>(void *,ObjectType,wmi::AutoRef<Subscription> &)
0x1800073eb  mov     rsi, [rsp+68h+arg_0]
0x1800073f0  test    byte ptr [rsi+58h], 2
0x1800073f4  jz      loc_180007570
0x1800073fa  lea     rdx, [rsi+28h]; struct SubscriptionWriteData *
0x1800073fe  mov     rax, [rdx]
0x180007401  mov     rbx, [rax+8]
0x180007405  xor     r8d, r8d; bool
0x180007408  call    ?Validate@EventSourceCollection@@AEBAXAEAVSubscriptionWriteData@@_N@Z; EventSourceCollection::Validate(SubscriptionWriteData &,bool)
0x18000740d  cmp     edi, [rbx+38h]
0x180007410  jnb     loc_18000750B
0x180007416  mov     r10d, [rbx+50h]
0x18000741a  mov     ecx, edi
0x18000741c  cmp     rdi, r10
0x18000741f  jnb     loc_1800074BB
0x180007425  lea     r8d, [rcx+1]
0x180007429  mov     r9d, r8d
0x18000742c  mov     rdx, [rbx+28h]
0x180007430  mov     eax, [rdx+r8*4]
0x180007434  mov     [rdx+rcx*4], eax
0x180007437  mov     ecx, r8d
0x18000743a  cmp     r9, r10
0x18000743d  jb      short loc_180007425
0x18000743f  mov     eax, edi
0x180007441  lea     r8d, [rax+1]
0x180007445  mov     r9d, r8d
0x180007448  mov     rdx, [rbx+58h]
0x18000744c  mov     ecx, eax
0x18000744e  mov     al, [rdx+r8]
0x180007452  mov     [rcx+rdx], al
0x180007455  mov     eax, r8d
0x180007458  cmp     r9, r10
0x18000745b  jb      short loc_180007441
0x18000745d  mov     eax, edi
0x18000745f  lea     r8d, [rax+1]
0x180007463  mov     r9d, r8d
0x180007466  mov     rdx, [rbx+40h]
0x18000746a  mov     ecx, eax
0x18000746c  mov     rax, [rdx+r8*8]
0x180007470  mov     [rdx+rcx*8], rax
0x180007474  mov     eax, r8d
0x180007477  cmp     r9, r10
0x18000747a  jb      short loc_18000745F
0x18000747c  mov     eax, edi
0x18000747e  lea     r8d, [rax+1]
0x180007482  mov     r9d, r8d
0x180007485  mov     rdx, [rbx+70h]
0x180007489  mov     ecx, eax
0x18000748b  mov     rax, [rdx+r8*8]
0x18000748f  mov     [rdx+rcx*8], rax
0x180007493  mov     eax, r8d
0x180007496  cmp     r9, r10
0x180007499  jb      short loc_18000747E
0x18000749b  lea     r8d, [rdi+1]
0x18000749f  mov     r9d, r8d
0x1800074a2  mov     rdx, [rbx+88h]
0x1800074a9  mov     ecx, edi
0x1800074ab  mov     rax, [rdx+r8*8]
0x1800074af  mov     [rdx+rcx*8], rax
0x1800074b3  mov     edi, r8d
0x1800074b6  cmp     r9, r10
0x1800074b9  jb      short loc_18000749B
0x1800074bb  or      eax, 0FFFFFFFFh
0x1800074be  add     [rbx+20h], eax
0x1800074c1  add     [rbx+50h], eax
0x1800074c4  add     [rbx+38h], eax
0x1800074c7  add     [rbx+68h], eax
0x1800074ca  add     [rbx+80h], eax
0x1800074d0  or      dword ptr [rbx+34h], 1
0x1800074d4  or      eax, 0FFFFFFFFh
0x1800074d7  lock xadd [rsi+8], eax
0x1800074dc  cmp     eax, 1
0x1800074df  jnz     short loc_1800074F9
0x1800074e1  test    rsi, rsi
0x1800074e4  jz      short loc_1800074F9
0x1800074e6  mov     rax, [rsi]
0x1800074e9  mov     edx, 1
0x1800074ee  mov     rcx, rsi
0x1800074f1  mov     rax, [rax]
0x1800074f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074f9  lea     r11, [rsp+68h+var_8]
0x1800074fe  mov     rbx, [r11+18h]
0x180007502  mov     rsi, [r11+20h]
0x180007506  mov     rsp, r11
0x180007509  pop     rdi
0x18000750a  retn
0x18000750b  lea     rax, WPP_GLOBAL_Control
0x180007512  mov     ebx, 57h ; 'W'
0x180007517  mov     rcx, cs:WPP_GLOBAL_Control
0x18000751e  cmp     rcx, rax
0x180007521  jz      short loc_180007545
0x180007523  test    byte ptr [rcx+1Ch], 1
0x180007527  jz      short loc_180007545
0x180007529  cmp     byte ptr [rcx+19h], 2
0x18000752d  jb      short loc_180007545
0x18000752f  lea     edx, [rbx-0Dh]
0x180007532  mov     r9d, ebx
0x180007535  lea     r8, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids
0x18000753c  mov     rcx, [rcx+10h]
0x180007540  call    WPP_SF_D
0x180007545  mov     r9d, 306h; int
0x18000754b  lea     r8, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x180007552  mov     edx, ebx; unsigned int
0x180007554  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180007559  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x18000755e  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180007565  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000756a  call    _CxxThrowException_0
0x180007570  lea     rax, WPP_GLOBAL_Control
0x180007577  mov     ebx, 10DDh
0x18000757c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007583  cmp     rcx, rax
0x180007586  jz      short loc_1800075AC
0x180007588  test    byte ptr [rcx+1Ch], 1
0x18000758c  jz      short loc_1800075AC
0x18000758e  cmp     byte ptr [rcx+19h], 2
0x180007592  jb      short loc_1800075AC
0x180007594  mov     edx, 49h ; 'I'
0x180007599  mov     r9d, ebx
0x18000759c  lea     r8, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids
0x1800075a3  mov     rcx, [rcx+10h]
0x1800075a7  call    WPP_SF_D
0x1800075ac  mov     r9d, 2F9h; int
0x1800075b2  lea     r8, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x1800075b9  mov     edx, ebx; unsigned int
0x1800075bb  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1800075c0  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x1800075c5  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800075cc  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800075d1  call    _CxxThrowException_0
```
