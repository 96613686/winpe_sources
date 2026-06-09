# _anonymous_namespace_::etw_cleanup

- ea: `0x18004be70`
- end: `0x18004bf1d`
- name: `_anonymous_namespace_::etw_cleanup`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180008660`
- `0x180042d60`
- `0x180042dd8`
- `0x180049ec0`
- `0x18004be70`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x18004bec0`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x18004bec0`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::etw_cleanup(struct lua_State *a1)
{
  __int64 v1; // rcx
  __int64 v2; // rcx
  __int64 *v3; // rbx
  const CHAR *v4; // rcx
  __int64 **v5; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  etw_module_state *v9; // [rsp+38h] [rbp+10h] BYREF

  v9 = (etw_module_state *)luaL_checkudata(a1, 1, "etw.state");
  lambda_2aca5f129b474aadbbf40af0d399ace1_::operator()__lambda_dd7849fe48b9404f0bef5e96356c469e___(v1, &v9);
  lambda_2aca5f129b474aadbbf40af0d399ace1_::operator()__lambda_098493ff884831594ffb32523a5cdedf___(v2, &v9);
  v3 = (__int64 *)**((_QWORD **)v9 + 1);
  while ( !*((_BYTE *)v3 + 25) )
  {
    v4 = (const CHAR *)(v3 + 4);
    if ( (unsigned __int64)v3[7] > 0xF )
      v4 = *(const CHAR **)v4;
    DeleteFileA(v4);
    v5 = (__int64 **)v3[2];
    if ( *((_BYTE *)v5 + 25) )
    {
      for ( i = (__int64 *)v3[1]; !*((_BYTE *)i + 25) && v3 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v3 = i;
      v3 = i;
    }
    else
    {
      v3 = (__int64 *)v3[2];
      for ( j = *v5; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v3 = j;
    }
  }
  etw_module_state::~etw_module_state(v9);
  return 0;
}

```

## disassembly

```asm
0x18004be70  push    rbx
0x18004be72  sub     rsp, 20h
0x18004be76  lea     r8, aEtwState; "etw.state"
0x18004be7d  mov     edx, 1; int
0x18004be82  call    ?luaL_checkudata@@YAPEAXPEAUlua_State@@HPEBD@Z; luaL_checkudata(lua_State *,int,char const *)
0x18004be87  lea     rdx, [rsp+28h+arg_8]
0x18004be8c  mov     [rsp+28h+arg_8], rax
0x18004be91  call    _lambda_2aca5f129b474aadbbf40af0d399ace1___operator____lambda_dd7849fe48b9404f0bef5e96356c469e___
0x18004be96  lea     rdx, [rsp+28h+arg_8]
0x18004be9b  call    _lambda_2aca5f129b474aadbbf40af0d399ace1___operator____lambda_098493ff884831594ffb32523a5cdedf___
0x18004bea0  mov     rax, [rsp+28h+arg_8]
0x18004bea5  mov     rbx, [rax+8]
0x18004bea9  mov     rbx, [rbx]
0x18004beac  cmp     byte ptr [rbx+19h], 0
0x18004beb0  jnz     short loc_18004BF0B
0x18004beb2  cmp     qword ptr [rbx+38h], 0Fh
0x18004beb7  lea     rcx, [rbx+20h]
0x18004bebb  jbe     short loc_18004BEC0
0x18004bebd  mov     rcx, [rcx]; lpFileName
0x18004bec0  call    cs:__imp_DeleteFileA
0x18004bec6  mov     rcx, [rbx+10h]
0x18004beca  cmp     byte ptr [rcx+19h], 0
0x18004bece  jz      short loc_18004BEEE
0x18004bed0  mov     rax, [rbx+8]
0x18004bed4  jmp     short loc_18004BEE3
0x18004bed6  cmp     rbx, [rax+10h]
0x18004beda  jnz     short loc_18004BEE9
0x18004bedc  mov     rbx, rax
0x18004bedf  mov     rax, [rax+8]
0x18004bee3  cmp     byte ptr [rax+19h], 0
0x18004bee7  jz      short loc_18004BED6
0x18004bee9  mov     rbx, rax
0x18004beec  jmp     short loc_18004BEAC
0x18004beee  mov     rbx, rcx
0x18004bef1  mov     rcx, [rcx]
0x18004bef4  cmp     byte ptr [rcx+19h], 0
0x18004bef8  jnz     short loc_18004BEAC
0x18004befa  mov     rax, [rcx]
0x18004befd  mov     rbx, rcx
0x18004bf00  mov     rcx, rax
0x18004bf03  cmp     byte ptr [rax+19h], 0
0x18004bf07  jz      short loc_18004BEFA
0x18004bf09  jmp     short loc_18004BEAC
0x18004bf0b  mov     rcx, [rsp+28h+arg_8]; this
0x18004bf10  call    ??1etw_module_state@@QEAA@XZ; etw_module_state::~etw_module_state(void)
0x18004bf15  xor     eax, eax
0x18004bf17  add     rsp, 20h
0x18004bf1b  pop     rbx
0x18004bf1c  retn
```
