# wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x180017ad8`
- end: `0x180017b3f`
- name: `?IgnoreCurrentThread@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `103`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180017b50`
- `0x180035e30`
- `0x1800362e4`
- `0x180036740`
- `0x180036b44`
- `0x180036f20`
- `0x1800373a8`

## callees

- `0x18000e0e8`
- `0x180017ad8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017aee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017aee`

## pseudocode

```c
void __fastcall wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  __int64 v1; // rbx
  void *v2; // rdx
  unsigned int v3; // r8d
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_DWORD *)(a1 + 312) )
  {
    v1 = a1 + 288;
    if ( *(_DWORD *)(a1 + 312) != GetCurrentThreadId() )
      wil::details::in1diag3::Log_Hr(retaddr, v2, v3, (const char *)0x8007029CLL, v6);
    v4 = *(__int64 **)v1;
    *(_DWORD *)(v1 + 24) = 0;
    while ( 1 )
    {
      v5 = *v4;
      if ( !*v4 )
        break;
      if ( v5 == v1 )
      {
        *v4 = *(_QWORD *)(v1 + 16);
        break;
      }
      v4 = (__int64 *)(v5 + 16);
      *(_QWORD *)v1 = v5 + 16;
    }
    *(_QWORD *)v1 = 0;
  }
}

```

## disassembly

```asm
0x180017ad8  push    rbx; int
0x180017ada  sub     rsp, 20h
0x180017ade  cmp     dword ptr [rcx+138h], 0
0x180017ae5  jz      short loc_180017B39
0x180017ae7  lea     rbx, [rcx+120h]
0x180017aee  call    cs:__imp_GetCurrentThreadId
0x180017af4  cmp     [rbx+18h], eax
0x180017af7  jz      short loc_180017B09
0x180017af9  mov     rcx, [rsp+28h]; this
0x180017afe  mov     r9d, 8007029Ch; char *
0x180017b04  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180017b09  mov     rcx, [rbx]
0x180017b0c  mov     dword ptr [rbx+18h], 0
0x180017b13  jmp     short loc_180017B21
0x180017b15  cmp     rax, rbx
0x180017b18  jz      short loc_180017B2B
0x180017b1a  lea     rcx, [rax+10h]
0x180017b1e  mov     [rbx], rcx
0x180017b21  mov     rax, [rcx]
0x180017b24  test    rax, rax
0x180017b27  jnz     short loc_180017B15
0x180017b29  jmp     short loc_180017B32
0x180017b2b  mov     rax, [rbx+10h]
0x180017b2f  mov     [rcx], rax
0x180017b32  mov     qword ptr [rbx], 0
0x180017b39  add     rsp, 20h
0x180017b3d  pop     rbx
0x180017b3e  retn
```
