# ATL::CComCreator<ATL::CComAggObject<CElevateWlanUi>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003a90`
- end: `0x180003b83`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCElevateWlanUi@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800039a0`

## callees

- `0x1800011d0`
- `0x180003a90`
- `0x180003e5c`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CElevateWlanUi>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // edi
  char *v8; // rax
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  struct ATL::CAtlModule *v10; // rcx
  int v11; // ecx
  int v12; // eax
  int v13; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)operator new(0x58u);
  v9 = (struct _RTL_CRITICAL_SECTION *)v8;
  if ( v8 )
  {
    v10 = ATL::_pAtlModule;
    *((_DWORD *)v8 + 2) = 0;
    *(_QWORD *)v8 = &ATL::CComAggObject<CElevateWlanUi>::`vftable';
    *(_OWORD *)(v8 + 40) = 0;
    *(_OWORD *)(v8 + 56) = 0;
    *((_QWORD *)v8 + 9) = 0;
    v8[80] = 0;
    *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CElevateWlanUi>::`vftable';
    *((_QWORD *)v8 + 4) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v10 + 8LL))(v10);
    v11 = ATL::CComCriticalSection::Init(v9 + 1);
    if ( v11 >= 0 )
      LOBYTE(v9[2].DebugInfo) = 1;
    v12 = 0;
    if ( v11 < 0 )
      v12 = v11;
    v13 = 0;
    if ( v12 < 0 )
      v13 = v12;
    v7 = 0;
    if ( v13 < 0 )
      v7 = v13;
    if ( v7
      || (v7 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64, _QWORD *))v9->DebugInfo->Type)(
                 v9,
                 a2,
                 a3)) != 0 )
    {
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64))v9->DebugInfo->ProcessLocksList.Blink)(v9, 1);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180003a90  push    rbx
0x180003a92  push    rbp
0x180003a93  push    rsi
0x180003a94  push    rdi
0x180003a95  push    r14
0x180003a97  sub     rsp, 20h
0x180003a9b  mov     rsi, r8
0x180003a9e  mov     rbp, rdx
0x180003aa1  mov     r14, rcx
0x180003aa4  test    r8, r8
0x180003aa7  jnz     short loc_180003AB3
0x180003aa9  mov     eax, 80004003h
0x180003aae  jmp     loc_180003B78
0x180003ab3  mov     ecx, 58h ; 'X'; Size
0x180003ab8  mov     qword ptr [r8], 0
0x180003abf  mov     edi, 8007000Eh
0x180003ac4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003ac9  mov     rbx, rax
0x180003acc  test    rax, rax
0x180003acf  jz      loc_180003B76
0x180003ad5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003adc  xorps   xmm0, xmm0
0x180003adf  mov     dword ptr [rax+8], 0
0x180003ae6  lea     rax, ??_7?$CComAggObject@VCElevateWlanUi@@@ATL@@6B@; const ATL::CComAggObject<CElevateWlanUi>::`vftable'
0x180003aed  mov     [rbx], rax
0x180003af0  xor     eax, eax
0x180003af2  movups  xmmword ptr [rbx+28h], xmm0
0x180003af6  movups  xmmword ptr [rbx+38h], xmm0
0x180003afa  mov     [rbx+48h], rax
0x180003afe  mov     [rbx+50h], al
0x180003b01  lea     rax, ??_7?$CComContainedObject@VCElevateWlanUi@@@ATL@@6B@; const ATL::CComContainedObject<CElevateWlanUi>::`vftable'
0x180003b08  mov     [rbx+18h], rax
0x180003b0c  mov     [rbx+20h], r14
0x180003b10  mov     rax, [rcx]
0x180003b13  mov     rax, [rax+8]
0x180003b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b1c  lea     rcx, [rbx+28h]; this
0x180003b20  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003b25  mov     ecx, eax
0x180003b27  test    eax, eax
0x180003b29  js      short loc_180003B2F
0x180003b2b  mov     byte ptr [rbx+50h], 1
0x180003b2f  xor     eax, eax
0x180003b31  test    ecx, ecx
0x180003b33  cmovs   eax, ecx
0x180003b36  xor     ecx, ecx
0x180003b38  test    eax, eax
0x180003b3a  cmovs   ecx, eax
0x180003b3d  xor     edi, edi
0x180003b3f  test    ecx, ecx
0x180003b41  cmovs   edi, ecx
0x180003b44  test    edi, edi
0x180003b46  jnz     short loc_180003B62
0x180003b48  mov     rax, [rbx]
0x180003b4b  mov     r8, rsi
0x180003b4e  mov     rdx, rbp
0x180003b51  mov     rcx, rbx
0x180003b54  mov     rax, [rax]
0x180003b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b5c  mov     edi, eax
0x180003b5e  test    eax, eax
0x180003b60  jz      short loc_180003B76
0x180003b62  mov     rcx, [rbx]
0x180003b65  mov     edx, 1
0x180003b6a  mov     rax, [rcx+18h]
0x180003b6e  mov     rcx, rbx
0x180003b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b76  mov     eax, edi
0x180003b78  add     rsp, 20h
0x180003b7c  pop     r14
0x180003b7e  pop     rdi
0x180003b7f  pop     rsi
0x180003b80  pop     rbp
0x180003b81  pop     rbx
0x180003b82  retn
```
