# p9fs::AsyncTask::promise_type::promise_type(void)

- ea: `0x18000dad4`
- end: `0x18000dbcf`
- name: `??0promise_type@AsyncTask@p9fs@@QEAA@XZ`
- size: `251`
- prototype: `__int64 __fastcall(p9fs::AsyncTask::promise_type *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180017b10`
- `0x18002753c`

## callees

- `0x180004144`
- `0x180004c80`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000db3f`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000db3f`

## pseudocode

```c
p9fs::AsyncTask::promise_type *__fastcall p9fs::AsyncTask::promise_type::promise_type(
        p9fs::AsyncTask::promise_type *this)
{
  p9fs::AsyncTask::promise_type *result; // rax
  char *v3; // [rsp+20h] [rbp-18h]

  v3 = (char *)operator new(0xC8u);
  *(_OWORD *)v3 = 0;
  *((_DWORD *)v3 + 2) = 1;
  *((_DWORD *)v3 + 3) = 1;
  *(_QWORD *)v3 = &std::_Ref_count_obj2<p9fs::AsyncTask::Storage>::`vftable';
  memset_0(v3 + 32, 0, 0xA8u);
  *((_QWORD *)v3 + 2) = 0;
  *((_QWORD *)v3 + 3) = 0;
  __ExceptionPtrCreate(v3 + 16);
  *((_QWORD *)v3 + 4) = 2;
  *(_OWORD *)(v3 + 56) = 0;
  *(_OWORD *)(v3 + 72) = 0;
  *(_OWORD *)(v3 + 88) = 0;
  *((_QWORD *)v3 + 5) = 0;
  *((_QWORD *)v3 + 6) = 0;
  *((_DWORD *)v3 + 26) = -1;
  *((_DWORD *)v3 + 27) = 0;
  *((_QWORD *)v3 + 14) = 0;
  *((_QWORD *)v3 + 15) = 0;
  *((_OWORD *)v3 + 8) = 0;
  *((_OWORD *)v3 + 9) = 0;
  *((_OWORD *)v3 + 10) = 0;
  *((_QWORD *)v3 + 22) = 0;
  v3[184] = 0;
  *((_QWORD *)v3 + 24) = 0;
  result = this;
  *(_OWORD *)this = 0;
  *(_QWORD *)this = v3 + 16;
  *((_QWORD *)this + 1) = v3;
  return result;
}

```

## disassembly

```asm
0x18000dad4  mov     [rsp+arg_8], rbx
0x18000dad9  mov     [rsp+arg_10], rsi
0x18000dade  push    rdi
0x18000dadf  sub     rsp, 30h
0x18000dae3  mov     rsi, rcx
0x18000dae6  mov     [rsp+38h+var_18], rcx
0x18000daeb  mov     ecx, 0C8h; Size
0x18000daf0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000daf5  mov     rdi, rax
0x18000daf8  mov     [rsp+38h+var_18], rax
0x18000dafd  xorps   xmm0, xmm0
0x18000db00  xor     edx, edx; Val
0x18000db02  mov     r8d, 0A8h; Size
0x18000db08  movups  xmmword ptr [rax], xmm0
0x18000db0b  mov     eax, 1
0x18000db10  lea     rbx, [rdi+10h]
0x18000db14  mov     [rdi+8], eax
0x18000db17  lea     rcx, [rbx+10h]; void *
0x18000db1b  mov     [rdi+0Ch], eax
0x18000db1e  lea     rax, ??_7?$_Ref_count_obj2@UStorage@AsyncTask@p9fs@@@std@@6B@; const std::_Ref_count_obj2<p9fs::AsyncTask::Storage>::`vftable'
0x18000db25  mov     [rdi], rax
0x18000db28  call    memset_0
0x18000db2d  mov     rcx, rbx
0x18000db30  mov     qword ptr [rbx], 0
0x18000db37  mov     qword ptr [rbx+8], 0
0x18000db3f  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18000db45  mov     qword ptr [rbx+10h], 2
0x18000db4d  xorps   xmm0, xmm0
0x18000db50  movups  xmmword ptr [rbx+28h], xmm0
0x18000db54  xor     eax, eax
0x18000db56  movups  xmmword ptr [rbx+38h], xmm0
0x18000db5a  movups  xmmword ptr [rbx+48h], xmm0
0x18000db5e  mov     qword ptr [rbx+18h], 0
0x18000db66  mov     qword ptr [rbx+20h], 0
0x18000db6e  mov     dword ptr [rbx+58h], 0FFFFFFFFh
0x18000db75  mov     dword ptr [rbx+5Ch], 0
0x18000db7c  mov     qword ptr [rbx+60h], 0
0x18000db84  mov     qword ptr [rbx+68h], 0
0x18000db8c  movups  xmmword ptr [rbx+70h], xmm0
0x18000db90  movups  xmmword ptr [rbx+80h], xmm0
0x18000db97  movups  xmmword ptr [rbx+90h], xmm0
0x18000db9e  mov     [rbx+0A0h], rax
0x18000dba5  mov     [rbx+0A8h], al
0x18000dbab  mov     [rbx+0B0h], rax
0x18000dbb2  mov     rax, rsi
0x18000dbb5  movups  xmmword ptr [rsi], xmm0
0x18000dbb8  mov     [rsi], rbx
0x18000dbbb  mov     rbx, [rsp+38h+arg_8]
0x18000dbc0  mov     [rsi+8], rdi
0x18000dbc4  mov     rsi, [rsp+38h+arg_10]
0x18000dbc9  add     rsp, 30h
0x18000dbcd  pop     rdi
0x18000dbce  retn
```
