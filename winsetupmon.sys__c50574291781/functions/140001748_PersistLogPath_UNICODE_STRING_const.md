# PersistLogPath(_UNICODE_STRING const *)

- ea: `0x140001748`
- end: `0x1400018a0`
- name: `?PersistLogPath@@YAJPEBU_UNICODE_STRING@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x140002ffc`
- `0x14000362c`

## callees

- `0x140001748`
- `0x1400018a8`
- `0x140001a10`
- `0x140003944`
- `0x14000a680`
- `0x14000f9e0`
- `0x14000fa40`
- `0x14000fd40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001856`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001856`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400017a0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400017a0`

## string_xrefs

- `0x14000182c`: `Failed to allocate updated log path`
- `0x140001814`: `Failed to create updated log configuration (0x%08X)`

## pseudocode

```c
__int64 __fastcall PersistLogPath(const struct _UNICODE_STRING *a1)
{
  struct IWsmLogConfig *v2; // rdi
  int v3; // eax
  __int64 (__fastcall ***v4)(__int64); // rsi
  unsigned int v5; // ebx
  __int64 Length; // rbx
  PVOID PoolWithTag; // rax
  void *v8; // rbp
  __int64 (__fastcall **v9)(__int64); // rax
  int v10; // eax
  _QWORD v12[5]; // [rsp+20h] [rbp-28h] BYREF
  __int64 (__fastcall ***v13)(__int64); // [rsp+58h] [rbp+10h] BYREF
  struct IWsmLogConfig *v14; // [rsp+60h] [rbp+18h] BYREF

  v13 = 0;
  v2 = 0;
  v14 = 0;
  v3 = QueryLogConfig(&v13);
  v4 = v13;
  v5 = v3;
  if ( v3 >= 0 )
  {
    if ( !v13 )
      return v5;
    Length = a1->Length;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, Length + 2, 0x6E6D7377u);
    v8 = PoolWithTag;
    if ( ExPoolZeroingNativelySupported )
    {
      if ( PoolWithTag )
        goto LABEL_6;
    }
    else if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, Length + 2);
LABEL_6:
      memmove(v8, a1->Buffer, a1->Length);
      v9 = *v4;
      v12[0] = v8;
      v12[1] = *(_QWORD *)((*v9)((__int64)v4) + 8);
      v10 = CreateInstance((struct _WSM_LOG_CONFIG *const)v12, &v14);
      v2 = v14;
      v5 = v10;
      if ( v10 >= 0 )
        v5 = SetLogConfig((__int64)v14);
      else
        WriteLogMessage(3, L"Failed to create updated log configuration (0x%08X)", (unsigned int)v10);
      ExFreePoolWithTag(v8, 0x6E6D7377u);
LABEL_12:
      if ( v2 )
        (*(void (__fastcall **)(struct IWsmLogConfig *))(*(_QWORD *)v2 + 8LL))(v2);
      goto LABEL_14;
    }
    WriteLogMessage(3, L"Failed to allocate updated log path");
    v5 = -1073741670;
    goto LABEL_12;
  }
LABEL_14:
  if ( v4 )
    (*v4)[1]((__int64)v4);
  return v5;
}

```

## disassembly

```asm
0x140001748  mov     rax, rsp
0x14000174b  mov     [rax+8], rbx
0x14000174f  mov     [rax+20h], rbp
0x140001753  push    rsi
0x140001754  push    rdi
0x140001755  push    r14
0x140001757  sub     rsp, 30h
0x14000175b  mov     r14, rcx
0x14000175e  mov     qword ptr [rax+10h], 0
0x140001766  xor     edi, edi
0x140001768  lea     rcx, [rax+10h]
0x14000176c  mov     [rax+18h], rdi
0x140001770  call    QueryLogConfig
0x140001775  mov     rsi, [rsp+48h+arg_8]
0x14000177a  mov     ebx, eax
0x14000177c  test    eax, eax
0x14000177e  js      loc_140001876
0x140001784  test    rsi, rsi
0x140001787  jz      loc_14000188A
0x14000178d  movzx   ebx, word ptr [r14]
0x140001791  mov     r8d, 6E6D7377h; Tag
0x140001797  mov     ecx, 401h; PoolType
0x14000179c  lea     rdx, [rbx+2]; NumberOfBytes
0x1400017a0  call    cs:__imp_ExAllocatePoolWithTag
0x1400017a7  nop     dword ptr [rax+rax+00h]
0x1400017ac  cmp     cs:ExPoolZeroingNativelySupported, dil
0x1400017b3  mov     rbp, rax
0x1400017b6  jnz     short loc_140001827
0x1400017b8  test    rax, rax
0x1400017bb  jz      short loc_14000182C
0x1400017bd  lea     r8, [rbx+2]; Size
0x1400017c1  xor     edx, edx; Val
0x1400017c3  mov     rcx, rax; void *
0x1400017c6  call    memset
0x1400017cb  movzx   r8d, word ptr [r14]; Size
0x1400017cf  mov     rcx, rbp; void *
0x1400017d2  mov     rdx, [r14+8]; Src
0x1400017d6  call    memmove
0x1400017db  mov     rax, [rsi]
0x1400017de  mov     rcx, rsi
0x1400017e1  mov     [rsp+48h+var_28], rbp
0x1400017e6  mov     rax, [rax]
0x1400017e9  call    _guard_dispatch_icall
0x1400017ee  lea     rdx, [rsp+48h+arg_10]; struct IWsmLogConfig **
0x1400017f3  mov     rcx, [rax+8]
0x1400017f7  mov     [rsp+48h+var_20], rcx
0x1400017fc  lea     rcx, [rsp+48h+var_28]; struct _WSM_LOG_CONFIG *
0x140001801  call    ?CreateInstance@@YAJQEAU_WSM_LOG_CONFIG@@PEAPEAVIWsmLogConfig@@@Z; CreateInstance(_WSM_LOG_CONFIG * const,IWsmLogConfig * *)
0x140001806  mov     rdi, [rsp+48h+arg_10]
0x14000180b  mov     ebx, eax
0x14000180d  test    eax, eax
0x14000180f  jns     short loc_140001844
0x140001811  mov     r8d, eax
0x140001814  lea     rdx, aFailedToCreate; "Failed to create updated log configurat"...
0x14000181b  mov     ecx, 3
0x140001820  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140001825  jmp     short loc_14000184E
0x140001827  test    rbp, rbp
0x14000182a  jnz     short loc_1400017CB
0x14000182c  lea     rdx, aFailedToAlloca_7; "Failed to allocate updated log path"
0x140001833  mov     ecx, 3
0x140001838  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14000183d  mov     ebx, 0C000009Ah
0x140001842  jmp     short loc_140001862
0x140001844  mov     rcx, rdi
0x140001847  call    SetLogConfig
0x14000184c  mov     ebx, eax
0x14000184e  mov     edx, 6E6D7377h; Tag
0x140001853  mov     rcx, rbp; P
0x140001856  call    cs:__imp_ExFreePoolWithTag
0x14000185d  nop     dword ptr [rax+rax+00h]
0x140001862  test    rdi, rdi
0x140001865  jz      short loc_140001876
0x140001867  mov     rax, [rdi]
0x14000186a  mov     rcx, rdi
0x14000186d  mov     rax, [rax+8]
0x140001871  call    _guard_dispatch_icall
0x140001876  test    rsi, rsi
0x140001879  jz      short loc_14000188A
0x14000187b  mov     rax, [rsi]
0x14000187e  mov     rcx, rsi
0x140001881  mov     rax, [rax+8]
0x140001885  call    _guard_dispatch_icall
0x14000188a  mov     rbp, [rsp+48h+arg_18]
0x14000188f  mov     eax, ebx
0x140001891  mov     rbx, [rsp+48h+arg_0]
0x140001896  add     rsp, 30h
0x14000189a  pop     r14
0x14000189c  pop     rdi
0x14000189d  pop     rsi
0x14000189e  retn
```
