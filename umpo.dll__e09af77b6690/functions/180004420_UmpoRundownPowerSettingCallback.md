# UmpoRundownPowerSettingCallback

- ea: `0x180004420`
- end: `0x180004758`
- name: `UmpoRundownPowerSettingCallback`
- size: `824`
- prototype: `__int64 __fastcall(UUID *, UUID *, UUID *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004420`
- `0x180004e0c`
- `0x1800059c0`
- `0x180005cb4`
- `0x18000f3dc`
- `0x180010070`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000450a`
- `ntdll!RtlAllocateHeap` at `0x180004646`
- `ntdll!RtlAllocateHeap` at `0x18000450a`
- `ntdll!RtlAllocateHeap` at `0x180004646`
- `ntdll!RtlFreeHeap` at `0x1800045bb`
- `ntdll!RtlFreeHeap` at `0x1800046f4`
- `ntdll!RtlFreeHeap` at `0x1800045bb`
- `ntdll!RtlFreeHeap` at `0x1800046f4`
- `ntdll!EtwEventWrite` at `0x1800045a9`
- `ntdll!EtwEventWrite` at `0x1800046e2`
- `ntdll!EtwEventWrite` at `0x1800045a9`
- `ntdll!EtwEventWrite` at `0x1800046e2`

## pseudocode

```c
__int64 __fastcall UmpoRundownPowerSettingCallback(UUID *a1, UUID *a2, UUID *a3)
{
  int v6; // eax
  PVOID Heap; // rax
  void *v8; // rbx
  int ACValue; // eax
  PVOID v10; // rbx
  SIZE_T Size; // [rsp+50h] [rbp-79h] BYREF
  DWORD v13; // [rsp+58h] [rbp-71h] BYREF
  DWORD v14[5]; // [rsp+5Ch] [rbp-6Dh] BYREF
  _QWORD v15[4]; // [rsp+70h] [rbp-59h] BYREF
  char *v16; // [rsp+90h] [rbp-39h]
  __int64 v17; // [rsp+98h] [rbp-31h]
  DWORD *v18; // [rsp+A0h] [rbp-29h]
  __int64 v19; // [rsp+A8h] [rbp-21h]
  SIZE_T *p_Size; // [rsp+B0h] [rbp-19h]
  __int64 v21; // [rsp+B8h] [rbp-11h]
  PVOID v22; // [rsp+C0h] [rbp-9h]
  int v23; // [rsp+C8h] [rbp-1h]
  int v24; // [rsp+CCh] [rbp+3h]
  DWORD *v25; // [rsp+D0h] [rbp+7h]
  __int64 v26; // [rsp+D8h] [rbp+Fh]

  v15[2] = a2;
  v15[0] = a1;
  v14[0] = 0;
  Size = 0;
  v13 = 0;
  v15[1] = 16;
  v15[3] = 16;
  v14[1] = 4;
  if ( !(unsigned int)UmpoReadFromUserPowerKey(a3, a1, a2, 0, 0, 1u, 0, (BYTE *)&Size + 4, &v14[1], (int *)v14) )
  {
    v6 = UmpoInternalReadxCValue(0, a3, a1, 0, (__int64)a2, 0, 0, 0, (LPDWORD)&Size);
    if ( v6 )
    {
      if ( v6 != 50 && v6 != 2 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    else
    {
      Heap = RtlAllocateHeap(UmpoHeapHandle, 8u, (unsigned int)Size);
      v8 = Heap;
      if ( !Heap )
        return 0;
      if ( (unsigned int)UmpoInternalReadxCValue(0, a3, a1, 0, (__int64)a2, 0, &v13, (__int64)Heap, (LPDWORD)&Size) )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      else
      {
        v16 = (char *)&Size + 4;
        v17 = 4;
        v18 = &v13;
        v19 = 4;
        p_Size = &Size;
        v23 = Size;
        v25 = v14;
        v21 = 4;
        v22 = v8;
        v24 = 0;
        v26 = 4;
        EtwEventWrite(UmpoProviderHandle, UMPO_EVT_RUNDOWN_DC_POWER_SETTING, 7, v15);
      }
      RtlFreeHeap(UmpoHeapHandle, 0, v8);
    }
  }
  v14[1] = 4;
  if ( !(unsigned int)UmpoReadFromUserPowerKey(a3, a1, a2, 0, 0, 0, 0, (BYTE *)&Size + 4, &v14[1], (int *)v14) )
  {
    ACValue = UmpoReadACValue(0, a3, a1, 0, (__int64)a2, 0, 0, (DWORD *)&Size);
    if ( ACValue )
    {
      if ( ACValue != 50 && ACValue != 2 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    else
    {
      v10 = RtlAllocateHeap(UmpoHeapHandle, 8u, (unsigned int)Size);
      if ( v10 )
      {
        if ( (unsigned int)UmpoReadACValue(0, a3, a1, 0, (__int64)a2, &v13, (__int64)v10, (DWORD *)&Size) )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        else
        {
          v16 = (char *)&Size + 4;
          v17 = 4;
          v18 = &v13;
          v19 = 4;
          p_Size = &Size;
          v23 = Size;
          v25 = v14;
          v21 = 4;
          v22 = v10;
          v24 = 0;
          v26 = 4;
          EtwEventWrite(UmpoProviderHandle, UMPO_EVT_RUNDOWN_AC_POWER_SETTING, 7, v15);
        }
        RtlFreeHeap(UmpoHeapHandle, 0, v10);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004420  push    rbp
0x180004422  push    rbx
0x180004423  push    rsi
0x180004424  push    rdi
0x180004425  push    r12
0x180004427  push    r14
0x180004429  push    r15
0x18000442b  lea     rbp, [rsp-27h]
0x180004430  sub     rsp, 0F0h
0x180004437  mov     rax, cs:__security_cookie
0x18000443e  xor     rax, rsp
0x180004441  mov     [rbp+57h+var_40], rax
0x180004445  xor     r15d, r15d
0x180004448  mov     [rbp+57h+var_A0], rdx
0x18000444c  mov     r14, r8
0x18000444f  mov     [rbp+57h+var_B0], rcx
0x180004453  lea     rax, [rbp+57h+var_C4]
0x180004457  mov     [rbp+57h+var_C4], r15d
0x18000445b  mov     [rsp+120h+var_D8], rax; __int64
0x180004460  mov     rsi, rdx
0x180004463  lea     rax, [rbp+57h+var_C4+4]
0x180004467  mov     dword ptr [rbp+57h+Size], r15d
0x18000446b  mov     [rsp+120h+var_E0], rax; LPDWORD
0x180004470  lea     r12d, [r15+4]
0x180004474  lea     rax, [rbp+57h+Size+4]
0x180004478  mov     [rbp+57h+var_C8], r15d
0x18000447c  mov     [rsp+120h+var_E8], rax; __int64
0x180004481  mov     r8, rdx
0x180004484  mov     [rsp+120h+lpType], r15; lpType
0x180004489  mov     rdi, rcx
0x18000448c  mov     rdx, rcx
0x18000448f  mov     [rsp+120h+var_F8], 1; int
0x180004497  xor     r9d, r9d
0x18000449a  mov     [rsp+120h+var_100], r15b; char
0x18000449f  mov     rcx, r14; Uuid2
0x1800044a2  mov     dword ptr [rbp+57h+Size+4], r15d
0x1800044a6  mov     [rbp+57h+var_A8], 10h
0x1800044ae  mov     [rbp+57h+var_98], 10h
0x1800044b6  mov     [rbp+57h+var_C4+4], r12d
0x1800044ba  call    UmpoReadFromUserPowerKey
0x1800044bf  test    eax, eax
0x1800044c1  jnz     loc_1800045C1
0x1800044c7  lea     rax, [rbp+57h+Size]
0x1800044cb  xor     r9d, r9d
0x1800044ce  mov     [rsp+120h+var_E0], rax
0x1800044d3  mov     r8, rdi
0x1800044d6  mov     [rsp+120h+var_E8], r15
0x1800044db  mov     rdx, r14
0x1800044de  mov     [rsp+120h+lpType], r15
0x1800044e3  xor     ecx, ecx
0x1800044e5  mov     byte ptr [rsp+120h+var_F8], r15b
0x1800044ea  mov     qword ptr [rsp+120h+var_100], rsi
0x1800044ef  call    UmpoInternalReadxCValue
0x1800044f4  test    eax, eax
0x1800044f6  jnz     loc_18000471A
0x1800044fc  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x180004500  lea     edx, [rax+8]; Flags
0x180004503  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x18000450a  call    cs:__imp_RtlAllocateHeap
0x180004510  mov     rbx, rax
0x180004513  test    rax, rax
0x180004516  jz      loc_1800046FA
0x18000451c  lea     rax, [rbp+57h+Size]
0x180004520  xor     r9d, r9d
0x180004523  mov     [rsp+120h+var_E0], rax
0x180004528  mov     r8, rdi
0x18000452b  mov     [rsp+120h+var_E8], rbx
0x180004530  lea     rax, [rbp+57h+var_C8]
0x180004534  mov     [rsp+120h+lpType], rax
0x180004539  mov     rdx, r14
0x18000453c  mov     byte ptr [rsp+120h+var_F8], r15b
0x180004541  xor     ecx, ecx
0x180004543  mov     qword ptr [rsp+120h+var_100], rsi
0x180004548  call    UmpoInternalReadxCValue
0x18000454d  test    eax, eax
0x18000454f  jnz     loc_180004736
0x180004555  mov     rcx, cs:UmpoProviderHandle
0x18000455c  lea     rax, [rbp+57h+Size+4]
0x180004560  mov     [rbp+57h+var_90], rax
0x180004564  lea     r9, [rbp+57h+var_B0]
0x180004568  lea     rax, [rbp+57h+var_C8]
0x18000456c  mov     [rbp+57h+var_88], r12
0x180004570  mov     [rbp+57h+var_80], rax
0x180004574  lea     r8d, [r15+7]
0x180004578  lea     rax, [rbp+57h+Size]
0x18000457c  mov     [rbp+57h+var_78], r12
0x180004580  mov     [rbp+57h+var_70], rax
0x180004584  lea     rdx, UMPO_EVT_RUNDOWN_DC_POWER_SETTING
0x18000458b  mov     eax, dword ptr [rbp+57h+Size]
0x18000458e  mov     [rbp+57h+var_58], eax
0x180004591  lea     rax, [rbp+57h+var_C4]
0x180004595  mov     [rbp+57h+var_50], rax
0x180004599  mov     [rbp+57h+var_68], r12
0x18000459d  mov     [rbp+57h+var_60], rbx
0x1800045a1  mov     [rbp+57h+var_54], r15d
0x1800045a5  mov     [rbp+57h+var_48], r12
0x1800045a9  call    cs:__imp_EtwEventWrite
0x1800045af  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x1800045b6  mov     r8, rbx; P
0x1800045b9  xor     edx, edx; Flags
0x1800045bb  call    cs:__imp_RtlFreeHeap
0x1800045c1  lea     rax, [rbp+57h+var_C4]
0x1800045c5  mov     [rbp+57h+var_C4+4], r12d
0x1800045c9  mov     [rsp+120h+var_D8], rax; __int64
0x1800045ce  xor     r9d, r9d
0x1800045d1  lea     rax, [rbp+57h+var_C4+4]
0x1800045d5  mov     r8, rsi
0x1800045d8  mov     [rsp+120h+var_E0], rax; LPDWORD
0x1800045dd  mov     rdx, rdi
0x1800045e0  lea     rax, [rbp+57h+Size+4]
0x1800045e4  mov     rcx, r14; Uuid2
0x1800045e7  mov     [rsp+120h+var_E8], rax; __int64
0x1800045ec  mov     [rsp+120h+lpType], r15; lpType
0x1800045f1  mov     [rsp+120h+var_F8], r15d; int
0x1800045f6  mov     [rsp+120h+var_100], r15b; char
0x1800045fb  call    UmpoReadFromUserPowerKey
0x180004600  test    eax, eax
0x180004602  jnz     loc_1800046FA
0x180004608  lea     rax, [rbp+57h+Size]
0x18000460c  xor     r9d, r9d
0x18000460f  mov     [rsp+120h+var_E8], rax
0x180004614  mov     r8, rdi
0x180004617  mov     [rsp+120h+lpType], r15
0x18000461c  mov     rdx, r14
0x18000461f  mov     qword ptr [rsp+120h+var_F8], r15
0x180004624  xor     ecx, ecx
0x180004626  mov     qword ptr [rsp+120h+var_100], rsi
0x18000462b  call    UmpoReadACValue
0x180004630  test    eax, eax
0x180004632  jnz     loc_180004740
0x180004638  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x18000463c  lea     edx, [rax+8]; Flags
0x18000463f  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180004646  call    cs:__imp_RtlAllocateHeap
0x18000464c  mov     rbx, rax
0x18000464f  test    rax, rax
0x180004652  jz      loc_1800046FA
0x180004658  lea     rax, [rbp+57h+Size]
0x18000465c  xor     r9d, r9d
0x18000465f  mov     [rsp+120h+var_E8], rax
0x180004664  mov     r8, rdi
0x180004667  lea     rax, [rbp+57h+var_C8]
0x18000466b  mov     [rsp+120h+lpType], rbx
0x180004670  mov     qword ptr [rsp+120h+var_F8], rax
0x180004675  mov     rdx, r14
0x180004678  xor     ecx, ecx
0x18000467a  mov     qword ptr [rsp+120h+var_100], rsi
0x18000467f  call    UmpoReadACValue
0x180004684  test    eax, eax
0x180004686  jnz     loc_180004751
0x18000468c  mov     rcx, cs:UmpoProviderHandle
0x180004693  lea     rax, [rbp+57h+Size+4]
0x180004697  mov     [rbp+57h+var_90], rax
0x18000469b  lea     r9, [rbp+57h+var_B0]
0x18000469f  lea     rax, [rbp+57h+var_C8]
0x1800046a3  mov     [rbp+57h+var_88], r12
0x1800046a7  mov     [rbp+57h+var_80], rax
0x1800046ab  lea     rdx, UMPO_EVT_RUNDOWN_AC_POWER_SETTING
0x1800046b2  lea     rax, [rbp+57h+Size]
0x1800046b6  mov     [rbp+57h+var_78], r12
0x1800046ba  mov     [rbp+57h+var_70], rax
0x1800046be  mov     r8d, 7
0x1800046c4  mov     eax, dword ptr [rbp+57h+Size]
0x1800046c7  mov     [rbp+57h+var_58], eax
0x1800046ca  lea     rax, [rbp+57h+var_C4]
0x1800046ce  mov     [rbp+57h+var_50], rax
0x1800046d2  mov     [rbp+57h+var_68], r12
0x1800046d6  mov     [rbp+57h+var_60], rbx
0x1800046da  mov     [rbp+57h+var_54], r15d
0x1800046de  mov     [rbp+57h+var_48], r12
0x1800046e2  call    cs:__imp_EtwEventWrite
0x1800046e8  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x1800046ef  mov     r8, rbx; P
0x1800046f2  xor     edx, edx; Flags
0x1800046f4  call    cs:__imp_RtlFreeHeap
0x1800046fa  xor     eax, eax
0x1800046fc  mov     rcx, [rbp+57h+var_40]
0x180004700  xor     rcx, rsp; StackCookie
0x180004703  call    __security_check_cookie
0x180004708  add     rsp, 0F0h
0x18000470f  pop     r15
0x180004711  pop     r14
0x180004713  pop     r12
0x180004715  pop     rdi
0x180004716  pop     rsi
0x180004717  pop     rbx
0x180004718  pop     rbp
0x180004719  retn
0x18000471a  cmp     eax, 32h ; '2'
0x18000471d  jz      loc_1800045C1
0x180004723  cmp     eax, 2
0x180004726  jz      loc_1800045C1
0x18000472c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180004731  jmp     loc_1800045C1
0x180004736  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000473b  jmp     loc_1800045AF
0x180004740  cmp     eax, 32h ; '2'
0x180004743  jz      short loc_1800046FA
0x180004745  cmp     eax, 2
0x180004748  jz      short loc_1800046FA
0x18000474a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000474f  jmp     short loc_1800046FA
0x180004751  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180004756  jmp     short loc_1800046E8
```
