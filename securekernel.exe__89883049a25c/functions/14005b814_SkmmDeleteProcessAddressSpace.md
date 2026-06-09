# SkmmDeleteProcessAddressSpace

- ea: `0x14005b814`
- end: `0x14005b9dd`
- name: `SkmmDeleteProcessAddressSpace`
- size: `457`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14006aaa0`
- `0x1400af6c0`

## callees

- `0x1400010f0`
- `0x140002e40`
- `0x140006b20`
- `0x14000db40`
- `0x14000e460`
- `0x140022db8`
- `0x140024724`
- `0x14005b814`
- `0x14007115c`
- `0x14009b778`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
void *__fastcall SkmmDeleteProcessAddressSpace(__int64 a1)
{
  void *result; // rax
  __int64 v3; // rcx
  __int64 v4; // rbx
  char v5; // al
  __int64 v6; // rdx
  __int64 v7; // r9
  _QWORD *v8; // r8
  __int64 v9; // rbx
  __int64 *v10; // rdx
  __int64 *v11; // rcx
  int v12; // ebx
  __int64 v13; // r8
  __int64 v14; // rdx
  _QWORD v15[4]; // [rsp+20h] [rbp-138h] BYREF
  signed __int32 v16[64]; // [rsp+40h] [rbp-118h] BYREF

  result = memset_0(v16, 0, sizeof(v16));
  v3 = *(_QWORD *)(a1 + 72);
  if ( v3 )
  {
    if ( (*(_DWORD *)a1 & 0x400) != 0 )
    {
      v4 = v3 + 256;
      v5 = SkAcquireSpinLockExclusive(v3 + 256);
      v6 = a1 + 360;
      v7 = *(_QWORD *)(a1 + 360);
      if ( *(_QWORD *)(v7 + 8) != a1 + 360 || (v8 = *(_QWORD **)(a1 + 368), *v8 != v6) )
        __fastfail(3u);
      *v8 = v7;
      LOBYTE(v6) = v5;
      *(_QWORD *)(v7 + 8) = v8;
      SkReleaseSpinLockExclusive(v4, v6);
      v9 = SkiAttachProcess(a1);
      SkmiFlushEnclaveContainerAddressSpace(a1, 0, 0x7FFFFFFEFLL, 0);
      v10 = *(__int64 **)(a1 + 72);
      v11 = SkmiSystemPartition;
      v15[0] = 0;
      v15[1] = 0;
      if ( v10 )
        v11 = v10;
      v15[2] = v11;
      SkmiFlushEnclaveContainerAddressSpace(a1, 0, 0x7FFFFFFEFLL, v15);
      SkmiEndDeferFreePages(v15);
      SkiAttachProcess(v9);
    }
    v12 = 0;
    memset_0(v16, 0, sizeof(v16));
    v14 = 0;
    if ( (_DWORD)SkeNumberProcessors )
    {
      do
      {
        v13 = SkeProcessorBlock[v14];
        if ( *(_QWORD *)(v13 + 64) == a1 )
        {
          _interlockedbittestandset(&v16[(unsigned __int64)(unsigned int)v14 >> 5], v14 & 0x1F);
          ++v12;
        }
        _InterlockedCompareExchange64((volatile signed __int64 *)(v13 + 2968), 0, *(_QWORD *)(v13 + 64));
        v14 = (unsigned int)(v14 + 1);
      }
      while ( (unsigned int)v14 < (unsigned int)SkeNumberProcessors );
      if ( v12 )
        SkeGenericIpiCall(v16, 0, SkmiDeselectAddressSpace, a1);
    }
    SkmiFreePhysicalPage(*(__int64 **)(a1 + 72), *(_QWORD *)(a1 + 64) >> 12, v13);
    SkmmFreeProcessShadow(a1);
    return (void *)SkmiDereferencePartition(*(_QWORD *)(a1 + 72));
  }
  return result;
}

```

## disassembly

```asm
0x14005b814  mov     [rsp+arg_8], rbx
0x14005b819  mov     [rsp+arg_10], rsi
0x14005b81e  push    rdi
0x14005b81f  sub     rsp, 150h
0x14005b826  mov     rax, cs:__security_cookie
0x14005b82d  xor     rax, rsp
0x14005b830  mov     [rsp+158h+var_18], rax
0x14005b838  mov     rdi, rcx
0x14005b83b  xor     edx, edx; Val
0x14005b83d  lea     rcx, [rsp+158h+var_118]; void *
0x14005b842  mov     r8d, 100h; Size
0x14005b848  call    memset_0
0x14005b84d  mov     rcx, [rdi+48h]
0x14005b851  test    rcx, rcx
0x14005b854  jz      loc_14005B9B0
0x14005b85a  test    dword ptr [rdi], 400h
0x14005b860  jz      loc_14005B919
0x14005b866  lea     rbx, [rcx+100h]
0x14005b86d  mov     rcx, rbx
0x14005b870  call    SkAcquireSpinLockExclusive
0x14005b875  lea     rdx, [rdi+168h]
0x14005b87c  mov     r9, [rdx]
0x14005b87f  cmp     [r9+8], rdx
0x14005b883  jnz     loc_14005B9D6
0x14005b889  mov     r8, [rdx+8]
0x14005b88d  cmp     [r8], rdx
0x14005b890  jnz     loc_14005B9D6
0x14005b896  mov     [r8], r9
0x14005b899  mov     dl, al
0x14005b89b  mov     rcx, rbx
0x14005b89e  mov     [r9+8], r8
0x14005b8a2  call    SkReleaseSpinLockExclusive
0x14005b8a7  mov     rcx, rdi
0x14005b8aa  call    SkiAttachProcess
0x14005b8af  mov     rsi, 7FFFFFFEFh
0x14005b8b9  xor     r9d, r9d
0x14005b8bc  mov     r8, rsi
0x14005b8bf  xor     edx, edx
0x14005b8c1  mov     rcx, rdi
0x14005b8c4  mov     rbx, rax
0x14005b8c7  call    SkmiFlushEnclaveContainerAddressSpace
0x14005b8cc  mov     rdx, [rdi+48h]
0x14005b8d0  lea     rcx, SkmiSystemPartition
0x14005b8d7  test    rdx, rdx
0x14005b8da  mov     [rsp+158h+var_138], 0
0x14005b8e3  lea     r9, [rsp+158h+var_138]
0x14005b8e8  mov     [rsp+158h+var_130], 0
0x14005b8f1  cmovnz  rcx, rdx
0x14005b8f5  mov     r8, rsi
0x14005b8f8  mov     [rsp+158h+var_128], rcx
0x14005b8fd  xor     edx, edx
0x14005b8ff  mov     rcx, rdi
0x14005b902  call    SkmiFlushEnclaveContainerAddressSpace
0x14005b907  lea     rcx, [rsp+158h+var_138]
0x14005b90c  call    SkmiEndDeferFreePages
0x14005b911  mov     rcx, rbx
0x14005b914  call    SkiAttachProcess
0x14005b919  xor     edx, edx; Val
0x14005b91b  lea     rcx, [rsp+158h+var_118]; void *
0x14005b920  mov     r8d, 100h; Size
0x14005b926  xor     ebx, ebx
0x14005b928  call    memset_0
0x14005b92d  xor     edx, edx
0x14005b92f  cmp     cs:SkeNumberProcessors, edx
0x14005b935  jbe     short loc_14005B98E
0x14005b937  lea     r8, SkeProcessorBlock
0x14005b93e  mov     ecx, edx
0x14005b940  mov     r8, [r8+rdx*8]
0x14005b944  cmp     [r8+40h], rdi
0x14005b948  jnz     short loc_14005B95B
0x14005b94a  shr     rcx, 5
0x14005b94e  mov     eax, edx
0x14005b950  and     eax, 1Fh
0x14005b953  lock bts [rsp+rcx*4+158h+var_118], eax
0x14005b959  inc     ebx
0x14005b95b  mov     rax, [r8+40h]
0x14005b95f  xor     ecx, ecx
0x14005b961  lock cmpxchg [r8+0B98h], rcx
0x14005b96a  inc     edx
0x14005b96c  cmp     edx, cs:SkeNumberProcessors
0x14005b972  jb      short loc_14005B937
0x14005b974  test    ebx, ebx
0x14005b976  jz      short loc_14005B98E
0x14005b978  mov     r9, rdi
0x14005b97b  lea     r8, SkmiDeselectAddressSpace
0x14005b982  xor     edx, edx
0x14005b984  lea     rcx, [rsp+158h+var_118]
0x14005b989  call    SkeGenericIpiCall
0x14005b98e  mov     rdx, [rdi+40h]
0x14005b992  mov     rcx, [rdi+48h]
0x14005b996  shr     rdx, 0Ch
0x14005b99a  call    SkmiFreePhysicalPage
0x14005b99f  mov     rcx, rdi
0x14005b9a2  call    SkmmFreeProcessShadow
0x14005b9a7  mov     rcx, [rdi+48h]
0x14005b9ab  call    SkmiDereferencePartition
0x14005b9b0  mov     rcx, [rsp+158h+var_18]
0x14005b9b8  xor     rcx, rsp; StackCookie
0x14005b9bb  call    __security_check_cookie
0x14005b9c0  lea     r11, [rsp+158h+var_8]
0x14005b9c8  mov     rbx, [r11+18h]
0x14005b9cc  mov     rsi, [r11+20h]
0x14005b9d0  mov     rsp, r11
0x14005b9d3  pop     rdi
0x14005b9d4  retn
0x14005b9d6  mov     ecx, 3
0x14005b9db  int     29h; Win8: RtlFailFast(ecx)
```
