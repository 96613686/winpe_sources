# CVolume::CloseVolumeHandles(void *,CVolume::EHandleChangeReason)

- ea: `0x18000131c`
- end: `0x18000143f`
- name: `?CloseVolumeHandles@CVolume@@QEAAXPEAXW4EHandleChangeReason@1@@Z`
- size: `291`
- prototype: `void __fastcall(__int64, __int64, int)`
- caller_count: `6`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180001008`
- `0x18000756c`
- `0x18000bd24`
- `0x18000d0a4`
- `0x18000d4dc`
- `0x18000f510`

## callees

- `0x18000131c`
- `0x1800015f0`
- `0x18000d2f8`
- `0x18000da90`

## import_xrefs

- `ntdll!NtClose` at `0x180001421`
- `ntdll!NtClose` at `0x180001421`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001380`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001380`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000140f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000140f`

## pseudocode

```c
void __fastcall CVolume::CloseVolumeHandles(__int64 a1, __int64 a2, int a3)
{
  volatile signed __int32 *v6; // r14
  void *v7; // rdi
  int v8; // eax
  BOOL v9; // ecx
  int v10; // eax

  if ( a2 && a2 != *(_QWORD *)(a1 + 2872) )
    return;
  v6 = (volatile signed __int32 *)(a1 + 2952);
  if ( !(unsigned int)BeginSingleInstanceTask((int *)(a1 + 2952)) )
    return;
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 208));
  ++*(_DWORD *)(a1 + 56);
  v8 = *(_DWORD *)(a1 + 16);
  v9 = (v8 & 8) != 0 || (v8 & 0x10) != 0;
  if ( a2 )
  {
    if ( a3 )
    {
      if ( a3 != 1 )
        goto LABEL_14;
      v10 = v8 | 0x10;
    }
    else
    {
      v10 = v8 | 8;
    }
    *(_DWORD *)(a1 + 16) = v10;
  }
LABEL_14:
  if ( !v9 )
  {
    CObjIdIndexChangeNotifier::StopListeningAndClose((CObjIdIndexChangeNotifier *)(a1 + 576));
    CLogFile::CloseLog((CLogFile *)(a1 + 312));
    if ( *(_QWORD *)(a1 + 24) )
    {
      v7 = *(void **)(a1 + 24);
      *(_QWORD *)(a1 + 24) = 0;
    }
  }
  --*(_DWORD *)(a1 + 56);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 208));
  _InterlockedDecrement(v6);
  if ( v7 )
    NtClose(v7);
}

```

## disassembly

```asm
0x18000131c  mov     [rsp+arg_0], rbx
0x180001321  mov     [rsp+arg_10], rsi
0x180001326  push    rdi
0x180001327  push    r12
0x180001329  push    r13
0x18000132b  push    r14
0x18000132d  push    r15
0x18000132f  sub     rsp, 30h
0x180001333  mov     r13d, r8d
0x180001336  mov     r15, rdx
0x180001339  mov     rbx, rcx
0x18000133c  test    rdx, rdx
0x18000133f  jz      short loc_18000134E
0x180001341  cmp     rdx, [rcx+0B38h]
0x180001348  jnz     loc_180001427
0x18000134e  lea     r14, [rcx+0B88h]
0x180001355  mov     [rsp+58h+arg_8], r14
0x18000135a  mov     rcx, r14; int *
0x18000135d  call    ?BeginSingleInstanceTask@@YAHPEAJ@Z; BeginSingleInstanceTask(long *)
0x180001362  test    eax, eax
0x180001364  jz      loc_180001427
0x18000136a  xor     edi, edi
0x18000136c  mov     [rsp+58h+var_38], rdi
0x180001371  lea     r12, [rbx+0D0h]
0x180001378  mov     [rsp+58h+arg_18], r12
0x18000137d  mov     rcx, r12; lpCriticalSection
0x180001380  call    cs:__imp_EnterCriticalSection
0x180001386  lea     rsi, [rbx+38h]
0x18000138a  mov     [rsp+58h+var_30], rsi
0x18000138f  inc     dword ptr [rsi]
0x180001391  mov     eax, [rbx+10h]
0x180001394  test    al, 8
0x180001396  jnz     short loc_1800013A0
0x180001398  test    al, 10h
0x18000139a  jnz     short loc_1800013A0
0x18000139c  xor     ecx, ecx
0x18000139e  jmp     short loc_1800013A5
0x1800013a0  mov     ecx, 1
0x1800013a5  test    r15, r15
0x1800013a8  jz      short loc_1800013C0
0x1800013aa  test    r13d, r13d
0x1800013ad  jnz     short loc_1800013B4
0x1800013af  or      eax, 8
0x1800013b2  jmp     short loc_1800013BD
0x1800013b4  cmp     r13d, 1
0x1800013b8  jnz     short loc_1800013C0
0x1800013ba  or      eax, 10h
0x1800013bd  mov     [rbx+10h], eax
0x1800013c0  test    ecx, ecx
0x1800013c2  jnz     short loc_1800013F4
0x1800013c4  lea     rcx, [rbx+240h]; this
0x1800013cb  call    ?StopListeningAndClose@CObjIdIndexChangeNotifier@@QEAAXXZ; CObjIdIndexChangeNotifier::StopListeningAndClose(void)
0x1800013d0  lea     rcx, [rbx+138h]; this
0x1800013d7  call    ?CloseLog@CLogFile@@AEAAXXZ; CLogFile::CloseLog(void)
0x1800013dc  cmp     qword ptr [rbx+18h], 0
0x1800013e1  jz      short loc_1800013F4
0x1800013e3  mov     rdi, [rbx+18h]
0x1800013e7  mov     [rsp+58h+var_38], rdi
0x1800013ec  mov     qword ptr [rbx+18h], 0
0x1800013f4  jmp     short loc_18000140A
0x1800013f6  mov     rdi, [rsp+58h+var_38]
0x1800013fb  mov     r14, [rsp+58h+arg_8]
0x180001400  mov     r12, [rsp+58h+arg_18]
0x180001405  mov     rsi, [rsp+58h+var_30]
0x18000140a  dec     dword ptr [rsi]
0x18000140c  mov     rcx, r12; lpCriticalSection
0x18000140f  call    cs:__imp_LeaveCriticalSection
0x180001415  lock dec dword ptr [r14]
0x180001419  test    rdi, rdi
0x18000141c  jz      short loc_180001427
0x18000141e  mov     rcx, rdi; Handle
0x180001421  call    cs:__imp_NtClose
0x180001427  mov     rbx, [rsp+58h+arg_0]
0x18000142c  mov     rsi, [rsp+58h+arg_10]
0x180001431  add     rsp, 30h
0x180001435  pop     r15
0x180001437  pop     r14
0x180001439  pop     r13
0x18000143b  pop     r12
0x18000143d  pop     rdi
0x18000143e  retn
```
