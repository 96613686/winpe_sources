# ProcessGroupPolicy(ulong,void *,HKEY__ *,_GROUP_POLICY_OBJECTW *,_GROUP_POLICY_OBJECTW *,unsigned __int64,int *,ulong (*)(int,ushort *))

- ea: `0x1800133f0`
- end: `0x1800134a3`
- name: `?ProcessGroupPolicy@@YAKKPEAXPEAUHKEY__@@PEAU_GROUP_POLICY_OBJECTW@@2_KPEAHP6AKHPEAG@Z@Z`
- size: `179`
- prototype: `unsigned int __fastcall(unsigned int, void *, HKEY, struct _GROUP_POLICY_OBJECTW *, struct _GROUP_POLICY_OBJECTW *, unsigned __int64, int *, unsigned int (*)(int, unsigned __int16 *))`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x1800133f0`
- `0x18001a7fc`
- `0x18001ac7c`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x180013470`
- `SHLWAPI!__imp_SHCreateThread` at `0x180013470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013485`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013485`

## pseudocode

```c
__int64 __fastcall ProcessGroupPolicy(
        int a1,
        void *a2,
        HKEY a3,
        struct _GROUP_POLICY_OBJECTW *a4,
        struct _GROUP_POLICY_OBJECTW *a5,
        unsigned __int64 a6,
        int *a7,
        unsigned int (*a8)(int, unsigned __int16 *))
{
  _DWORD *v12; // rax
  void *v13; // rbx
  unsigned int v14; // edi

  v12 = operator new(0x40u);
  v13 = v12;
  if ( v12 )
  {
    v14 = 0;
    v12[1] = 0;
    *((_QWORD *)v12 + 4) = a5;
    *((_QWORD *)v12 + 5) = a6;
    *v12 = a1;
    *((_QWORD *)v12 + 1) = a2;
    *((_QWORD *)v12 + 2) = a3;
    *((_QWORD *)v12 + 3) = a4;
    *((_QWORD *)v12 + 6) = a7;
    *((_QWORD *)v12 + 7) = a8;
    if ( !SHCreateThread((LPTHREAD_START_ROUTINE)ProcessGroupPolicyWorker, v12, 0x18u, 0) )
    {
      operator delete(v13, 0x40u);
      return GetLastError();
    }
  }
  else
  {
    return 14;
  }
  return v14;
}

```

## disassembly

```asm
0x1800133f0  push    rbx
0x1800133f2  push    rbp
0x1800133f3  push    rsi
0x1800133f4  push    rdi
0x1800133f5  push    r14
0x1800133f7  push    r15
0x1800133f9  sub     rsp, 28h
0x1800133fd  mov     r15d, ecx
0x180013400  mov     rsi, r9
0x180013403  mov     ecx, 40h ; '@'; unsigned __int64
0x180013408  mov     rbp, r8
0x18001340b  mov     r14, rdx
0x18001340e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013413  mov     rbx, rax
0x180013416  test    rax, rax
0x180013419  jz      short loc_18001348F
0x18001341b  mov     rcx, [rsp+58h+arg_20]
0x180013423  xor     edi, edi
0x180013425  mov     [rax+4], edi
0x180013428  xor     r9d, r9d; pfnCallback
0x18001342b  mov     [rax+20h], rcx
0x18001342f  mov     rdx, rbx; pData
0x180013432  mov     rcx, [rsp+58h+arg_28]
0x18001343a  mov     [rax+28h], rcx
0x18001343e  lea     r8d, [rdi+18h]; flags
0x180013442  mov     [rax], r15d
0x180013445  lea     rcx, ?ProcessGroupPolicyWorker@@YAKPEAX@Z; pfnThreadProc
0x18001344c  mov     [rax+8], r14
0x180013450  mov     [rax+10h], rbp
0x180013454  mov     [rax+18h], rsi
0x180013458  mov     rax, [rsp+58h+arg_30]
0x180013460  mov     [rbx+30h], rax
0x180013464  mov     rax, [rsp+58h+arg_38]
0x18001346c  mov     [rbx+38h], rax
0x180013470  call    cs:__imp_SHCreateThread
0x180013476  test    eax, eax
0x180013478  jnz     short loc_180013494
0x18001347a  lea     edx, [rdi+40h]; unsigned __int64
0x18001347d  mov     rcx, rbx; void *
0x180013480  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013485  call    cs:__imp_GetLastError
0x18001348b  mov     edi, eax
0x18001348d  jmp     short loc_180013494
0x18001348f  mov     edi, 0Eh
0x180013494  mov     eax, edi
0x180013496  add     rsp, 28h
0x18001349a  pop     r15
0x18001349c  pop     r14
0x18001349e  pop     rdi
0x18001349f  pop     rsi
0x1800134a0  pop     rbp
0x1800134a1  pop     rbx
0x1800134a2  retn
```
