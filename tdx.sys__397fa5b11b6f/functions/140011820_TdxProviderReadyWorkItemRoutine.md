# TdxProviderReadyWorkItemRoutine

- ea: `0x140011820`
- end: `0x140011984`
- name: `TdxProviderReadyWorkItemRoutine`
- size: `356`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000f364`
- `0x140011820`
- `0x140012fd0`
- `0x140013c84`
- `0x1400151d0`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x140011973`
- `ntoskrnl!KeSetTimer` at `0x140011973`
- `ntoskrnl!IoFreeWorkItem` at `0x1400118e2`
- `ntoskrnl!IoFreeWorkItem` at `0x1400118e2`
- `TDI!TdiProviderReady` at `0x140011899`
- `TDI!TdiProviderReady` at `0x140011899`

## string_xrefs

- `0x1400118c3`: `TdxProviderReadyWorkItemRoutine`
- `0x14001192a`: `TdxProviderReadyWorkItemRoutine`

## pseudocode

```c
void __fastcall TdxProviderReadyWorkItemRoutine(PDEVICE_OBJECT DeviceObject, PVOID Context, __int64 a3)
{
  __int32 v3; // ecx
  __int32 v4; // ecx

  v3 = _InterlockedExchange((_DWORD *)&qword_14001E508 + 1, 0) - 1;
  if ( !v3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        47,
        (unsigned int)WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids,
        (unsigned int)"TdxProviderReadyWorkItemRoutine",
        WPP_MAIN_CB.ActiveThreadCount);
    }
    if ( (unsigned __int8)TdxDecrementNotReadyInterfaceCount(2461) )
      goto LABEL_13;
LABEL_20:
    _InterlockedExchange((_DWORD *)&qword_14001E508 + 1, 3);
    KeSetTimer(&TdxProviderReadyContext, (LARGE_INTEGER)-570000000LL, &Dpc);
    return;
  }
  v4 = v3 - 1;
  if ( !v4 )
    goto LABEL_20;
  if ( v4 != 1 )
    return;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)&qword_14001E508, 1, 0) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 48, a3, WPP_MAIN_CB.ActiveThreadCount);
    }
    TdiProviderReady(TdxTdiProviderHandle);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_s(
        WPP_GLOBAL_Control->AttachedDevice,
        49,
        WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids,
        "TdxProviderReadyWorkItemRoutine");
    }
  }
LABEL_13:
  IoFreeWorkItem(qword_14001E500);
  _InterlockedExchange64((volatile __int64 *)&qword_14001E500, 0);
}

```

## disassembly

```asm
0x140011820  mov     [rsp+arg_0], rbx
0x140011825  push    rsi
0x140011826  sub     rsp, 30h
0x14001182a  xor     ecx, ecx
0x14001182c  mov     ebx, 3
0x140011831  xchg    ecx, dword ptr cs:qword_14001E508+4
0x140011837  sub     ecx, 1
0x14001183a  jz      loc_140011903
0x140011840  sub     ecx, 1
0x140011843  jz      loc_140011958
0x140011849  cmp     ecx, 1
0x14001184c  jnz     loc_1400118F7
0x140011852  xor     eax, eax
0x140011854  lock cmpxchg dword ptr cs:qword_14001E508, ecx
0x14001185c  jnz     short loc_1400118DB
0x14001185e  mov     rcx, cs:WPP_GLOBAL_Control
0x140011865  lea     rsi, WPP_GLOBAL_Control
0x14001186c  cmp     rcx, rsi
0x14001186f  jz      short loc_140011892
0x140011871  cmp     [rcx+29h], bl
0x140011874  jb      short loc_140011892
0x140011876  test    dword ptr [rcx+2Ch], 200h
0x14001187d  jz      short loc_140011892
0x14001187f  mov     r9d, cs:WPP_MAIN_CB.ActiveThreadCount
0x140011886  lea     edx, [rbx+2Dh]
0x140011889  mov     rcx, [rcx+18h]
0x14001188d  call    WPP_SF_d
0x140011892  mov     rcx, cs:TdxTdiProviderHandle; ProviderHandle
0x140011899  call    cs:__imp_TdiProviderReady
0x1400118a0  nop     dword ptr [rax+rax+00h]
0x1400118a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400118ac  cmp     rcx, rsi
0x1400118af  jz      short loc_1400118DB
0x1400118b1  cmp     [rcx+29h], bl
0x1400118b4  jb      short loc_1400118DB
0x1400118b6  test    dword ptr [rcx+2Ch], 200h
0x1400118bd  jz      short loc_1400118DB
0x1400118bf  mov     rcx, [rcx+18h]
0x1400118c3  lea     r9, aTdxproviderrea_0; "TdxProviderReadyWorkItemRoutine"
0x1400118ca  mov     edx, 31h ; '1'
0x1400118cf  lea     r8, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids
0x1400118d6  call    WPP_SF_s
0x1400118db  mov     rcx, cs:qword_14001E500; IoWorkItem
0x1400118e2  call    cs:__imp_IoFreeWorkItem
0x1400118e9  nop     dword ptr [rax+rax+00h]
0x1400118ee  xor     eax, eax
0x1400118f0  xchg    rax, cs:qword_14001E500
0x1400118f7  mov     rbx, [rsp+38h+arg_0]
0x1400118fc  add     rsp, 30h
0x140011900  pop     rsi
0x140011901  retn
0x140011903  mov     rcx, cs:WPP_GLOBAL_Control
0x14001190a  lea     rsi, WPP_GLOBAL_Control
0x140011911  cmp     rcx, rsi
0x140011914  jz      short loc_14001194A
0x140011916  cmp     [rcx+29h], bl
0x140011919  jb      short loc_14001194A
0x14001191b  test    dword ptr [rcx+2Ch], 200h
0x140011922  jz      short loc_14001194A
0x140011924  mov     eax, cs:WPP_MAIN_CB.ActiveThreadCount
0x14001192a  lea     r9, aTdxproviderrea_0; "TdxProviderReadyWorkItemRoutine"
0x140011931  mov     rcx, [rcx+18h]
0x140011935  lea     r8, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids
0x14001193c  mov     edx, 2Fh ; '/'
0x140011941  mov     [rsp+38h+var_18], eax
0x140011945  call    WPP_SF_sd
0x14001194a  mov     ecx, 99Dh
0x14001194f  call    TdxDecrementNotReadyInterfaceCount
0x140011954  test    al, al
0x140011956  jnz     short loc_1400118DB
0x140011958  xchg    ebx, dword ptr cs:qword_14001E508+4
0x14001195e  lea     r8, Dpc; Dpc
0x140011965  mov     rdx, 0FFFFFFFFDE067D80h; DueTime
0x14001196c  lea     rcx, TdxProviderReadyContext; Timer
0x140011973  call    cs:__imp_KeSetTimer
0x14001197a  nop     dword ptr [rax+rax+00h]
0x14001197f  jmp     loc_1400118F7
```
