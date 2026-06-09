# IServerConfiguration::SubscribeAndGetDynamicStringSetting(wchar_t const *,wchar_t const *,void (*)(wchar_t const *,wchar_t const *,wchar_t const *,void *),void *,wchar_t const *)

- ea: `0x10044e410`
- end: `0x10044e50f`
- name: `?SubscribeAndGetDynamicStringSetting@IServerConfiguration@@QEAA_NPEB_W0P6AX000PEAX@Z10@Z`
- size: `255`
- prototype: `bool __fastcall(IServerConfiguration *__hidden this, const wchar_t *, const wchar_t *, void (*)(const wchar_t *, const wchar_t *, const wchar_t *, void *), void *, const wchar_t *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x100412470`
- `0x10042a380`

## callees

- `0x10044e410`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10044e4ec`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044e4ec`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044e49b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044e49b`
- `sqldk!SystemThread_TlsOffset` at `0x10044e480`
- `sqldk!SystemThread_TlsIndex` at `0x10044e477`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IServerConfiguration::SubscribeAndGetDynamicStringSetting(
        IServerConfiguration *this,
        const wchar_t *a2,
        const wchar_t *a3,
        void (__fastcall *a4)(const wchar_t *, const wchar_t *, void *, void *),
        void *a5,
        const wchar_t *a6)
{
  const wchar_t *v10; // r12
  void *v11; // r14
  __int64 result; // rax
  __int64 v13; // rbx
  __int64 v14; // r9
  unsigned __int8 v15; // bl
  void *v16; // [rsp+70h] [rbp+8h] BYREF

  v10 = a6;
  v11 = a5;
  result = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 8LL))(*((_QWORD *)this + 3));
  if ( (_BYTE)result )
  {
    v16 = 0;
    v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v14 = *(_QWORD *)(v13 + 256);
    if ( !v14 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v14 = *(_QWORD *)(v13 + 256);
    }
    if ( (***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, void **, const wchar_t *))this
            + 3))(
           *((_QWORD *)this + 3),
           a2,
           a3,
           *(_QWORD *)(v14 + 1000),
           &v16,
           v10) )
    {
      a4(a2, a3, v16, v11);
      v15 = 1;
    }
    else
    {
      v15 = 0;
    }
    operator delete[](v16);
    return v15;
  }
  return result;
}

```

## disassembly

```asm
0x10044e410  mov     r11, rsp
0x10044e413  push    rsi
0x10044e414  push    rdi
0x10044e415  push    r12
0x10044e417  push    r14
0x10044e419  push    r15
0x10044e41b  sub     rsp, 40h
0x10044e41f  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x10044e427  mov     [r11+10h], rbx
0x10044e42b  mov     [r11+18h], rbp
0x10044e42f  mov     rbp, r9
0x10044e432  mov     rdi, r8
0x10044e435  mov     rsi, rdx
0x10044e438  mov     r15, rcx
0x10044e43b  mov     rcx, [rcx+18h]
0x10044e43f  mov     rax, [rcx]
0x10044e442  mov     r12, [rsp+68h+arg_28]
0x10044e44a  mov     [r11-40h], r12
0x10044e44e  mov     r14, [rsp+68h+arg_20]
0x10044e456  mov     [r11-48h], r14
0x10044e45a  call    qword ptr [rax+8]
0x10044e45d  test    al, al
0x10044e45f  jz      loc_10044E4F5
0x10044e465  mov     [rsp+68h+arg_0], 0
0x10044e46e  mov     rdx, gs:58h
0x10044e477  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044e47e  mov     ecx, [rax]
0x10044e480  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044e487  mov     ebx, [rax]
0x10044e489  add     rbx, [rdx+rcx*8]
0x10044e48d  mov     r9, [rbx+100h]
0x10044e494  test    r9, r9
0x10044e497  jnz     short loc_10044E4A8
0x10044e499  xor     ecx, ecx
0x10044e49b  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044e4a1  mov     r9, [rbx+100h]
0x10044e4a8  mov     rcx, [r15+18h]
0x10044e4ac  mov     rax, [rcx]
0x10044e4af  mov     [rsp+68h+var_40], r12
0x10044e4b4  lea     rdx, [rsp+68h+arg_0]
0x10044e4b9  mov     [rsp+68h+var_48], rdx
0x10044e4be  mov     r9, [r9+3E8h]
0x10044e4c5  mov     r8, rdi
0x10044e4c8  mov     rdx, rsi
0x10044e4cb  call    qword ptr [rax]
0x10044e4cd  test    al, al
0x10044e4cf  jnz     short loc_10044E4D5
0x10044e4d1  xor     bl, bl
0x10044e4d3  jmp     short loc_10044E4E7
0x10044e4d5  mov     r9, r14
0x10044e4d8  mov     r8, [rsp+68h+arg_0]
0x10044e4dd  mov     rdx, rdi
0x10044e4e0  mov     rcx, rsi
0x10044e4e3  call    rbp
0x10044e4e5  mov     bl, 1
0x10044e4e7  mov     rcx, [rsp+68h+arg_0]
0x10044e4ec  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10044e4f2  movzx   eax, bl
0x10044e4f5  mov     rbx, [rsp+68h+arg_8]
0x10044e4fa  mov     rbp, [rsp+68h+arg_10]
0x10044e502  add     rsp, 40h
0x10044e506  pop     r15
0x10044e508  pop     r14
0x10044e50a  pop     r12
0x10044e50c  pop     rdi
0x10044e50d  pop     rsi
0x10044e50e  retn
```
